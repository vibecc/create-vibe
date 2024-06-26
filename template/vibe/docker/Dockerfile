FROM vibecc/vibe

RUN mkdir myApp
COPY . /myApp
WORKDIR /myApp

RUN g++ -std=c++17 App.cpp -o App -L. -lvibe

EXPOSE 8080
CMD [ "./App" ]
