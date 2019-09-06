vue-cli 3 inc. babel, typescript, devserver en ui tool. Installeer   npm install -g @vue/cli. Bekijk versie: vue --version
vuex is voor state management (centrale opslag van componenten)
vue-js dev tools chrome extensions

#1. maak je eerste project: 

    vue create test
    cd test
    npm run serve

#2. je kunt ook opstarten vue ui

    cd ..
    vue ui



#3. open project hier in vscode

    - single page is index.html met 'app'  als placeholder. Zie 'main.js' die een nieuwe vue instantie injecteert in div met id 'app'.
    - app.vue is de component. met altijd:
        # template
        # script
        # style (globaal)


    Let nu op dat de <template> in HelloWorld.vue altijd 1 child <div> moet hebben. Daarin is vrij aanpasbaar.

    <HelloWorld msg="Welcome to Your Vue.js App"/> wijst naar HelloWorld.vue geimporteerd met: 
    import HelloWorld from './components/HelloWorld.vue'

    export default {
    name: 'app',
    components: {
        HelloWorld
    }
    }

+++++++++++++++++++++++++++++++++++++++++++++++++
+++++++++++++++ INTERESSANT 
+++++++++++++++++++++++++++++++++++++++++++++++++


jsonrestapi fake backend rest api. Zie https://jsonplaceholder.typicode.com/todos
http library : npm  i axios

SHORTCUT voor commentaar; ALT + SHIFT + A

installeer router via de plugin (al app.vue overriden)

DEPLOY npm run build of via dasboard / tasks / build

of gebruik https://www.netlify.com

GIT in vscode -> CMD + SHIFT + P opent command box => Git: Clone
