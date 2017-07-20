---
layout: post
title: FormatJS指南 1 - Basic Internationalization Principles
tags: 原创 技术 翻译 React
---

[原文](https://formatjs.io/guides/basic-i18n/)

    <section id="toc"></section>

    <section class="secs">
        <h2 id="what-and-why">
            What Is Internationalization and Why Does It Matter?
        </h2>

        <p>
            Internationalized software supports the languages and cultural customs of people throughout the world. The Web reaches all parts of the world. Internationalized web apps provide a great user experience for people everywhere.
        </p>

        <p>
            Localized software adapts to a specific language and culture by translating text into the user's language and formatting data in accordance with the user's expectations. An app is typically localized for a small set of <a href="#locales">locales</a>.
        </p>

        <p>
            The <a href="http://www.ecma-international.org/ecma-402/1.0/index.html#sec-4.1">ECMA-402 JavaScript internalization specification</a> has an excellent overview.
        </p>
    </section>

    <section class="secs">
        <h2 id="locales">
            Locales: Language and Region
        </h2>

        <p>
            A "locale" refers to the lingual and cultural expectations for a region. It is represented using a "locale code" defined in <a href="http://tools.ietf.org/html/bcp47">BCP 47</a>.
        </p>

        <p>
            This code is comprised of several parts separated by hyphens ({{code "-"}}). The first part is a short string representing the language.
            The second, optional, part is a short string representing the region. Additionally, various extensions and variants can be specified.
        </p>

        <p>
            Typically, web apps are localized to just the language or language-region combination. Examples of such locale codes are:
        </p>

        <ul>
            <li>
                {{code "en"}} for English
            </li>
            <li>
                {{code "en-US"}} for English as spoken in the United States
            </li>
            <li>
                {{code "en-GB"}} for English as spoken in the United Kingdom
            </li>
            <li>
                {{code "es-AR"}} for Spanish as spoken in Argentina
            </li>
            <li>
                {{code "ar-001"}} for Arabic as spoken throughout the world
            </li>
            <li>
                {{code "ar-AE"}} for Arabic as spoken in United Arab Emirates
            </li>
        </ul>

        <p>
            Most internationalized apps only support a small list of locales.
        </p>
    </section>

    <section class="secs">
        <h2 id="translating-strings">
            Translating Strings
        </h2>

        <p>
            You likely have some text in your application that is in a natural language such as English or Japanese. In order to support other locales, you will need to translate these strings.
        </p>

        <p>
            {{brand}} provides a mechanism to let you write the core "software" of your application without special code for different translations. The considerations for each locale are encapsulated in your translated strings and our libraries.
        </p>

{{#code "js"}}
var messages = {
    en: {
        GREETING: 'Hello {name}'
    },
    fr: {
        GREETING: 'Bonjour {name}'
    }
};
{{/code}}

        <p>
            We use the <a href="http://userguide.icu-project.org/formatparse/messages">ICU Message</a> syntax which is also used in <a href="http://docs.oracle.com/javase/7/docs/api/java/text/MessageFormat.html">Java</a> and <a href="http://php.net/manual/en/class.messageformatter.php">PHP</a>.
        </p>
    </section>

    <section class="secs">
        <h2 id="bundling-translations">
            Bundling Translated Strings
        </h2>

        <p>
            It is common to organize your translations primarily by locale, because you only need the translations for the user's current locale. Our <a href="{{pathTo 'integrations'}}">template and component library integrations</a> are designed to work with the translations for a single locale. If your app is complex, you can further subdivide your translations, such as by page or section of the site.
        </p>
    </section>

    <section class="secs">
        <h2 id="structure-code">
            Structure of Code
        </h2>

        <p>
            The actual formatting and presentation of data and translated strings typically takes these steps:
        </p>

        <ol>
            <li>
                Determine the user's locale, as described in <a href="{{pathTo 'guides' guide='runtime-environments'}}">Runtime Environments</a> guide.
            </li>

            <li>
                Setup one of {{brand}}'s <a href="{{pathTo 'integrations'}}">integrations</a> with the following data:
                <ul>
                    <li>
                        the user's current locale
                    </li>
                    <li>
                        translated strings for that locale
                    </li>
                    <li>
                        optionally, any <a href="{{pathTo 'guides' guide='message-syntax'}}#custom-formats">custom formats</a>
                    </li>
                </ul>
            </li>

            <li>
                Call the template engine, passing the data that needs formatting.
            </li>
        </ol>
    </section>
