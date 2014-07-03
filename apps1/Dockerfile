FROM michielbdejong/apps
RUN cd litewrite && mkdir public/
RUN cd litewrite && mv index.html public/
RUN cd litewrite && mv litewrite.js public/
RUN cd litewrite && git checkout -- .
RUN cd litewrite && git branch master
RUN cd litewrite && git checkout master
RUN cd litewrite && rm -r src/
RUN cd litewrite && rm -r lib/
RUN cd litewrite && mv public/* .
RUN cd litewrite && rmdir public
RUN cd litewrite && git commit -am"build"
