# Continuing with Nuxt content

Default Injected Variables
* body: body text
* dir: directory
* extension: file extension (.md in this example)
* path: the file path
* slug: the file slug
* toc: an array containing our table of contents
* createdAt: the file creation date
* updatedAt: the date of the last file update

-> we can access all these variables by using the article variable. 

### Date Formatting

we can format dates by creating a method that takes in a date and returns a new date with the options of 
year, month, and day formatted to how we want

methods: {

formatDate(date) {

const options = { year: 'numeric', month: 'long', day: 'numeric' }

return new Date(date).toLocaleDateString('en', options)

}

}

### Custom Injected Variables
* To add custom injected variables, we should add a block of YAML front matter to our md file. 
* It must be at the TOP of the file and must be a valid YAML format set between three triple dashed lines.
* Useful for adding SEO variables, such as titles, descriptions, and images.


### Styling our Markdown Contents
* we can add styles to all of our elements coming from our md file by wrapping them in the nuxt-content class.

for ex,   .nuxt-content h2 {

font-weight: bold;

font-size: 28px;
}

### Creating a previous and next component

 * we use a v-if inside our NuxtLink component to see if there is a previous blog post and if there is we add a link to it.


#### problems that I'm facing with...
-> Missing required prop: "document" 
it says I have an error in my slug.vue component file.
Worked on it for two days in a row but couldn't find which line of code causes this error..
