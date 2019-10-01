FROM ruby:latest

WORKDIR /course

COPY . .

RUN bundle install

RUN apt-get install -y curl 

RUN curl -sL https://deb.nodesource.com/setup_10.x | bash
RUN apt-get install -y nodejs

#RUN rails db:migrate

EXPOSE 3000

CMD [ "rails", "s" ]