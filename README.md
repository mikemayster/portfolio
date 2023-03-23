# :boom: Personal portfolio built

## A minimal and clean portfolio!

![CSS3](https://img.shields.io/badge/css3-%231572B6.svg?style=for-the-badge&logo=css3&logoColor=white)
![HTML5](https://img.shields.io/badge/html5-%23E34F26.svg?style=for-the-badge&logo=html5&logoColor=white)
![Vue.js](https://img.shields.io/badge/vuejs-%2335495e.svg?style=for-the-badge&logo=vuedotjs&logoColor=%234FC08D)
![JavaScript](https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E)
![Nuxtjs](https://img.shields.io/badge/Nuxt-002E3B?style=for-the-badge&logo=nuxtdotjs&logoColor=#00DC82)
![Vuetify](https://img.shields.io/badge/Vuetify-1867C0?style=for-the-badge&logo=vuetify&logoColor=AEDDFF)
<br/>

The portfolio has been configured in `nuxt.config.js` in order to be deployed inside GitHub pages.<br/>

- Brief introduction about yourself and avatar image with email and other relevant point of contacts.
- Carrier experiences with skills divided by work place in a timeline.
- Work Projects.
- Add your Curriculum Vitae pdf within the portfolio.
- Mobile friendly.
  <br/>
  It does not require any backend or database integration, it is full front end!
  <br/><br/>

:satellite: Live Demo: [Click me!](https://mikemayster.github.io/m2m-folio/)

<br/>

### :computer: Technologies & Programming stuff

- **Vue** as main JavaScript framework.
- **Vuetify** as main Css framework.
- **HTML**
- **CSS**

### :hammer: How to run

1. Clone this repository into your local environment.
2. Edit entry `"name": "m2m-folio"` in your package.json file, give a proper name to it!
3. Run `npm install`
4. Run `npm run start`
5. Open _localhost:8080_ or whichever url it will be prompt in the console and see if it is working correctly.
6. Push it to your repository with a nice name for your personal portfolio.

### :file_folder: Sections

The portfolio is highly customizable, if you don't need a particular route (menu entry), you can deactivate it using the configuration inside `src/router/router.json` <br/>
The configuration should be straightforward, every entry can be enabled or disabled using the boolean value:

    "icon": "mdi-gamepad-variant",
    "title": "Inspire",
    "isEnabled": true,
    "to": "/inspire"

By changing the **title** value you will modify the label on the navigation menu.

### :pencil2: Portfolio Content

You simply need to edit some simple `json` files to change the content of your portfolio, there will be one for every section.<br/>
In the home page you will have three sections( About me/Greeting, Skills layer and Career timeline)

### :newspaper: Home

Here you will have thre sections:

1. About me/Greeting you can change by editing `components/greetings/greetings.json` file and add an entry to that providing simple informations like greeting, title, subTitle, caption, an image avatar and your contacts with additional icon and link. You can add multiple contacts as your relevant point of contacts. You can set a download link for your curriculum vitae by simply adding a file called `resume.pdf` inside the `static/resume` folder. If you don't need it you can disable it by simply disabling the property inside `components/greetings/greetings.json`.

2. Skills you can change by editing `components/skills/skills.json` file, is divided in three layers (Front End, Back End, Tools) and for each layer you can add how many skills you want by providing name, image and color. Is component a component that renders a different image of a burger depending on where the user hovers or clicks otherwise will change in sequence, with a timeout between one piece and another, you can se your own interval by changing the `burgerInterval`. This component is made up of a single div with the burger nested inside and a sibling div positioned absolutely with the same height and width as the image. The sibling div contains three child divs that each take up a third of the parent div's height. These three divs have event listeners that trigger state change and render a new burger image along with corresponding skills set. Each skills set is a component of its own that triggers an animation when interacted with. This component is built in Photoshop and utilizes HTML, CSS, and JavaScript.

3. Career you can change by editing `components/career/career.json` file and add an entry to that providing simple informations like title, timeline, image, and messagges. You can add multiple messagges as you want by providing simple informations like company, message, tags, time and color

### :newspaper: Projects

In order to make project available you will need to edit `components/projects/projects.json` file and add an entry to that providing simple informations like title, sections, text, and link. <br/>
The projects can be grouped under the globalSections object, which contains a title and icon, this object will be used to filter the section you want so search:

    ["All", "Game"]

By adding **section** you will be able to filter but remember that the section must be in globalSection object too.
<br/>

### :rainbow: Color schemes

M2M-folio supports also color schemes, by default you will find two different themes, a light and a dark one. <br/>
Don't worry, you will be able to choose your personal palette by modifying the file `config.json` and start customizing it with your own personal colors. <br/>

### :rocket: Deploy Nuxt on GitHub Pages

To deploy on GitHub Pages, you need to generate your static web application:<br/>
`npm run generate`<br/>
If you are creating GitHub Pages for one specific repository, and you don't have any custom domain, the URL of the page will be in this format: `http://<username>.github.io/<repository-name>`.<br/>
Then generate and deploy your static application:<br/>
`npm run deploy`
