# pnc - Preben-Norwegian-Community

This is the Github repo of Preben's norwegian community!

## The software

The software consists in a [Wordpress landing website](https://norwegiancommunity.com), that presents the content of the language courses and how it works. After that, there is the main [learning website](learn.prebenorwegian.com) that uses LearnWorlds as a service.

## The "coded" software

Each course-level users are divided in groups, that have some live lessons in different days of the week. This logic is external to LearnWorlds, so there was the need to automatize it and make a sort of "wrapper". The software in this Github repo has hence that goal

### How does it work

The admin (or the teachers) log in to an external, made in home, [platform](https://pnc.prebenorwegian.com). Here, they can see all the courses (gotten from LearnWorlds APIs) and handle the groups for each course. So, they can create/edit/remove groups and enroll/unenroll students from those groups. 

There are then some webcomponents that interface with this platform and are shown, after the user is logged in, in the courses' pages. These "widgets" allow the users to see the available groups for a course and to enroll/unenroll from the courses.

Through LearnWorlds web-hooks, if a user unenrolls from a course, he is automatically removed from his group.

### How was it made

Everything was developed with **Typescript**.

The repositories are:
* __[pnc-api](https://github.com/Preben-Norwegian-Community/pnc-api)__: The APIs of the project. Made with **Node.js** and **Express**. They interface with a **MongoDB** database and with the **LearnWorlds APIs**. It also hosts an **api-sdk**, a client published on npm to interface with the APIs in the frontend code.
* __[pnc-webapp](https://github.com/Preben-Norwegian-Community/pnc-webapp)__: The APIs of the project. Made with **Vue.js** and **Vuetify**.
* __[pnc-webcomponents](https://github.com/Preben-Norwegian-Community/pnc-webcomponents)__: The webcomponents shown on LearnWorlds. Made with **Vue.js** and **Vuetify**.
* __[pnc-learnworlds-snippets](https://github.com/Preben-Norwegian-Community/pnc-learnworlds-snippets)__: The snippets that are added to LearnWorlds custom code.
