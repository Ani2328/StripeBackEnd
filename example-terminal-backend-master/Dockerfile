FROM ruby:3.1.2

# Install build dependencies
RUN apk add --no-cache build-base libpq-dev sqlite-dev

# Install bundler
RUN gem install bundler:2.3.24

# Set up application directory
RUN mkdir -p /www/example-terminal-backend
WORKDIR /www/example-terminal-backend

# Copy application code
COPY . .

# Install Ruby gems
RUN bundle install

# Expose port (optional)
EXPOSE 4567

# Run the Ruby app, binding to 0.0.0.0 and using the PORT environment variable
ENTRYPOINT ["ruby", "web.rb", "-o", "0.0.0.0"]