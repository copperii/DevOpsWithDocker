FROM ruby:2.6.0

WORKDIR /course

COPY . .

#RUN date +%Y%m%d -s "20191003"
#RUN date -s "3 OCT 2019 11:59:00"
RUN date

RUN apt-get install -y curl 

RUN curl -sL https://deb.nodesource.com/setup_10.x | bash -
RUN apt-get install -y nodejs

RUN bundle install
RUN rails db:migrate RAILS_ENV=development

EXPOSE 3000

CMD [ "rails", "s" ]