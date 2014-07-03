FROM michielbdejong/devbox
#add remotestorage.js versions:
ADD remotestorage.js remotestorage.js
ADD remotestorage-nocache.js remotestorage-nocache.js
ADD remotestorage.min.js remotestorage.min.js

#prepare litewrite
RUN git clone https://github.com/apptorrent/litewrite.git
RUN cd litewrite ; git remote add 5apps git@5apps.com:michiel_litewrite.git
RUN cp remotestorage.js litewrite/lib/

#build litewrite
RUN cd litewrite ; npm install
RUN cd litewrite && mkdir public/
RUN cd litewrite && mv index.html public/
RUN cd litewrite && mv litewrite.js public/
RUN cd litewrite && git checkout -- .
RUN cd litewrite && git checkout origin/master -b master
#RUN cd litewrite && rm -r src/*
#RUN cd litewrite && rm -r lib/*
RUN cd litewrite && mv public/* .
RUN cd litewrite && rmdir public
RUN cd litewrite && git commit -am"build"

# prepare ghost
RUN git clone https://github.com/apptorrent/ghost.git
RUN cd ghost ; git remote add 5apps git@5apps.com:michiel_ghost-michiel.git
RUN cp remotestorage-nocache.js ghost/vendor/

# build ghost
RUN # cd ghost && git commit -am"build"

# prepare dogfeed
RUN git clone https://github.com/apptorrent/dogfeed.git
RUN cd dogfeed ; git remote add 5apps git@5apps.com:michiel_dogfeed-michiel.git
RUN cp remotestorage.min.js dogfeed/vendor/remotestorage/

# build dogfeed
RUN cd dogfeed && npm install
RUN cd dogfeed && grunt
RUN # cd dogfeed && git commit -am"build"

# prepare dogtalk
RUN git clone https://github.com/apptorrent/dogtalk.git
RUN cd dogtalk ; git remote add 5apps git@5apps.com:michiel_dogtalk-michiel.git
RUN cp remotestorage.min.js dogtalk/vendor/remotestorage/

# build dogtalk
RUN cd dogtalk && npm install
RUN cd dogtalk && grunt
RUN cd dogtalk && git add build/
RUN # cd dogtalk && git commit -am"build"

#RUN git clone https://github.com/skddc/sharesome.git
#RUN git clone https://github.com/xMartin/grouptabs.git
#RUN git clone https://github.com/diafygi/byoDB.git
#RUN git clone https://github.com/nilclass/remotestorage-browser-example.git
#RUN git clone https://github.com/shybyte/unhosted-time-tracker.git
#RUN git clone https://github.com/nilclass/svg-edit.git
#RUN git clone https://github.com/silverbucket/vidmarks.git
#RUN git clone https://github.com/michielbdejong/html-music-player.git
#RUN git clone https://github.com/remotestorage/myfavoritedrinks.git
#RUN git clone https://github.com/michielbdejong/todomvc.git
#RUN git clone https://github.com/nilclass/dspace-client.git
#RUN git clone https://github.com/tantaman/strut.git
#RUN git clone https://github.com/michielbdejong/meute.git
#RUN git clone https://github.com/michielbdejong/export.5apps.com.git
#RUN git clone https://github.com/michielbdejong/import.5apps.com.git
#RUN git clone https://github.com/unhosted/store.git
#
#RUN #cd laverna ; git remote add 5apps git@5apps.com/Laverna/laverna.git
#RUN #cd mcnotes ; git remote add 5apps git@5apps.com/mc96107/mcnotes.git
#RUN #cd  ; git remote add 5apps git@5apps.com/skddc/sharesome.git
#RUN cd grouptabs ; git remote add 5apps git@5apps.com:michiel_grouptabs.git
#RUN #cd  ; git remote add 5apps git@5apps.com/diafygi/byoDB.git
#RUN cd remotestorage-browser-example ; git remote add 5apps git@5apps.com:michiel_browser-michiel.git
#RUN cd unhosted-time-tracker ; git remote add 5apps git@5apps.com:michiel_unhosted-time-tracker.git
#RUN cd svg-edit ; git remote add 5apps git@5apps.com:michiel_svg-edit.git
#RUN cd vidmarks ; git remote add 5apps git@5apps.com:michiel_vidmarks.git
#RUN cd html-music-player ; git remote add 5apps git@5apps.com:michiel_music.git
#RUN cd myfavoritedrinks ; git remote add 5apps git@5apps.com:xmartin_myfavoritedrinks.git
#RUN cd todomvc ; git remote add 5apps git@5apps.com:michiel_todomvc.git
#RUN cd dspace-client ; git remote add 5apps git@5apps.com:michiel_dspace-client-michiel.git
#RUN #cd  ; git remote add 5apps git@5apps.com/tantaman/strut.git
#RUN cd meute ; git remote add 5apps git@5apps.com:michiel_august.git
#RUN cd export.5apps.com ; git remote add 5apps git@5apps.com:michiel_export.git
#RUN cd import.5apps.com ; git remote add 5apps git@5apps.com:michiel_import.git
#RUN cd store ; git remote add 5apps git@5apps.com:michiel_store.git
#
#RUN npm install -g grunt-cli
#RUN cd litewrite ; npm install
#
#RUN wget http://remotestorage.io/release/0.10.0/remotestorage.js
#RUN wget http://remotestorage.io/release/0.10.0/remotestorage.min.js
#RUN wget http://remotestorage.io/release/0.10.0/remotestorage-nocache.js
#
#RUN cp remotestorage.js litewrite/lib/
#RUN cp remotestorage-nocache.js ghost/vendor/
#RUN cp remotestorage.min.js dogfeed/vendor/remotestorage/
#RUN cp remotestorage.min.js dogtalk/vendor/remotestorage/
#RUN cp remotestorage-nocache.js sharesome/vendor/remotestorage/
#RUN cp remotestorage.js remotestorage-browser-example/lib/
#RUN cp remotestorage.js unhosted-time-tracker/libs/remote-storage/remoteStorage-debug.js
#RUN cp remotestorage.min.js svg-edit/editor/extensions/ext-remotestorage/
#RUN cp remotestorage.js vidmarks/vendor/remoteStorage.js
#RUN cp remotestorage.js html-music-player/ext/js/
#RUN cp remotestorage.js myfavoritedrinks/
#RUN cp remotestorage.js todomvc/labs/architecture-examples/remotestorage/js/
#RUN cp remotestorage.js dspace-client/deps/remoteStorage.js
#RUN cp remotestorage.js meute/upstream/
#RUN cp remotestorage.js import.5apps.com/vendor/
#RUN cp remotestorage.js export.5apps.com/vendor/
#RUN cp remotestorage.js store/
#
#RUN cd litewrite ; grunt build
