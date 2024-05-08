# Use Node.js image as base
FROM node:18

# Set working directory inside the container
WORKDIR /app/my-vue-project

# Copy package.json and package-lock.json files to the container
COPY package*.json ./

# Install dependencies
RUN npm install

# Install Vue CLI globally
RUN npm install -g @vue/cli
RUN npm install @vue/cli-service --save-dev


# Create Vue.js project with Vue 3 and skip prompts
RUN vue create my-vue-project --preset default --default


# Install Tailwind CSS
RUN npm install tailwindcss

# Install postcss-cli for processing Tailwind CSS
RUN npm install postcss-cli

# Install autoprefixer for adding vendor prefixes to CSS
RUN npm install autoprefixer

# Create Tailwind CSS configuration file
RUN npx tailwindcss init

# Install ShadowCSS
RUN npm install shadcn-vue

# Expose port 8080 to the outside world
EXPOSE 8080

# Start the application
CMD ["npm", "run", "serve"]
