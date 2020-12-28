---
description: >-
  Xip Kit includes everything you need to build amazing conversational bots with
  tools you know and love.
---

# Xip Kit

![](.gitbook/assets/logo.svg)

## What's Xip Kit?

Xip Kit \(or just Xip\) is an open source Ruby framework for conversational voice and text chatbots.

Xip is inspired by the Model-View-Controller \(MVC\) pattern. However, instead of calling them _Views,_ Xip refers to them as _Replies_ to better match the chatbot domain.

* The [Model](https://hellostealth.org/docs/#models) layer represents your data model \(such as Account, User, Quote, etc.\) and encapsulates the business logic that is specific to your bot. By default, Xip uses [ActiveRecord](https://hellostealth.org/docs/#models.active_record), but you can use any library that you prefer.
* The [Controller](https://hellostealth.org/docs/#controllers) layer is responsible for handling incoming requests from messaging platforms and providing and transmitting the response \(reply\).
* The [Reply](https://hellostealth.org/docs/#replies) layer is composed of “templates” that are responsible for constructing the respective response.

In addition to being inspired by Model-View-Controller \(MVC\) pattern, Xip as a few other awesome things built in for you.

* **Plug and play components.** Every service integration in Xip is a Ruby gem. One bot can support multiple [me](https://hellostealth.org/docs/#messaging_integrations)ssaging platforms \(i.e. Facebook Messenger, SMS, Alexa, and more\) and multiple NLP/NLU services.
* **Innovative.** Xip is constantly improving and evolving. There are many innovations in Xip such as: interrupt detection, homophone detection, hot-code reloading, multi-level catch-all handling, and more that make your bots perform better.
* **Advanced tooling.** From web servers to continuous integration testing, Xip is built to take advantage of all the great work done by the web development community.
* **Hosting you know.** Xip bots are Rack applications. That means your bots can be [deployed](https://hellostealth.org/docs/#deployment) using familiar services like Docker and Heroku.
* **Ready for production.** Xip already powers bots for large, well-known brands. So your next bot project is in good hands.
* **Open source.** Xip Kit is MIT licensed to ensure you own your bot. More importantly, we welcome contributors to help make Xip even better for everyone.

