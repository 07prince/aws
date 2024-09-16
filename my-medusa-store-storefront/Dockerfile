FROM node:20.17.0

# Set the working directory inside the container
WORKDIR /usr/src/app

# Copy package.json and package-lock.json to leverage Docker caching
COPY package.json ./
COPY package-lock.json ./

# Install dependencies
RUN npm install

# Copy the rest of your application files
COPY . .

# Copy .env file
ENV NEXT_PUBLIC_MEDUSA_BACKEND_URL=http://172.19.0.4:9000
ENV NEXT_PUBLIC_BASE_URL=http://localhost:8000
ENV NEXT_PUBLIC_DEFAULT_REGION=us
ENV NEXT_PUBLIC_STRIPE_KEY=
ENV NEXT_PUBLIC_PAYPAL_CLIENT_ID=
ENV NEXT_PUBLIC_SEARCH_APP_ID=
ENV NEXT_PUBLIC_SEARCH_ENDPOINT=http://127.0.0.1:7700
ENV NEXT_PUBLIC_SEARCH_API_KEY=
ENV NEXT_PUBLIC_INDEX_NAME=products
ENV REVALIDATE_SECRET=supersecret

# Expose the port your application runs on
EXPOSE 8000

# Run the application in development mode
CMD ["npm", "run", "dev"]
