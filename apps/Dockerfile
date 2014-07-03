FROM michielbdejong/devbox
RUN git clone https://github.com/litewrite/litewrite.git
RUN git clone https://github.com/Laverna/laverna.git
RUN git clone https://github.com/mc96107/mcnotes.git
RUN git clone https://github.com/vcuculo/ghost.git
RUN git clone https://github.com/silverbucket/dogfeed.git
RUN git clone https://github.com/silverbucket/dogtalk.git
RUN git clone https://github.com/skddc/sharesome.git
RUN git clone https://github.com/xMartin/grouptabs.git
RUN git clone https://github.com/diafygi/byoDB.git
RUN git clone https://github.com/nilclass/remotestorage-browser-example.git
RUN git clone https://github.com/shybyte/unhosted-time-tracker.git
RUN git clone https://github.com/nilclass/svg-edit.git
RUN git clone https://github.com/silverbucket/vidmarks.git
RUN git clone https://github.com/michielbdejong/html-music-player.git
RUN git clone https://github.com/remotestorage/myfavoritedrinks.git
RUN git clone https://github.com/michielbdejong/todomvc.git
RUN git clone https://github.com/nilclass/dspace-client.git
RUN git clone https://github.com/tantaman/strut.git
RUN git clone https://github.com/michielbdejong/meute.git
RUN git clone https://github.com/michielbdejong/export.5apps.com.git
RUN git clone https://github.com/michielbdejong/import.5apps.com.git
RUN git clone https://github.com/unhosted/store.git

RUN cd litewrite ; git remote add 5apps git@5apps.com:michiel_litewrite.git
RUN #cd laverna ; git remote add 5apps git@5apps.com/Laverna/laverna.git
RUN #cd mcnotes ; git remote add 5apps git@5apps.com/mc96107/mcnotes.git
RUN cd ghost ; git remote add 5apps git@5apps.com:michiel_ghost.git
RUN cd dogfeed ; git remote add 5apps git@5apps.com:michiel_dogfeed.git
RUN cd dogtalk ; git remote add 5apps git@5apps.com:michiel_dogtalk.git
RUN #cd  ; git remote add 5apps git@5apps.com/skddc/sharesome.git
RUN cd grouptabs ; git remote add 5apps git@5apps.com:michiel_grouptabs.git
RUN #cd  ; git remote add 5apps git@5apps.com/diafygi/byoDB.git
RUN cd remotestorage-browser-example ; git remote add 5apps git@5apps.com:michiel_browser-michiel.git
RUN cd unhosted-time-tracker ; git remote add 5apps git@5apps.com:michiel_unhosted-time-tracker.git
RUN cd svg-edit ; git remote add 5apps git@5apps.com:michiel_svg-edit.git
RUN cd vidmarks ; git remote add 5apps git@5apps.com:michiel_vidmarks.git
RUN cd html-music-player ; git remote add 5apps git@5apps.com:michiel_music.git
RUN cd myfavoritedrinks ; git remote add 5apps git@5apps.com:xmartin_myfavoritedrinks.git
RUN cd todomvc ; git remote add 5apps git@5apps.com:michiel_todomvc.git
RUN cd dspace-client ; git remote add 5apps git@5apps.com:michiel_dspace-client-michiel.git
RUN #cd  ; git remote add 5apps git@5apps.com/tantaman/strut.git
RUN cd meute ; git remote add 5apps git@5apps.com:michiel_august.git
RUN cd export.5apps.com ; git remote add 5apps git@5apps.com:michiel_export.git
RUN cd import.5apps.com ; git remote add 5apps git@5apps.com:michiel_import.git
RUN cd store ; git remote add 5apps git@5apps.com:michiel_store.git

RUN npm install -g grunt-cli
RUN cd litewrite ; npm install

RUN wget http://remotestorage.io/release/0.10.0/remotestorage.js
RUN wget http://remotestorage.io/release/0.10.0/remotestorage.min.js
RUN wget http://remotestorage.io/release/0.10.0/remotestorage-nocache.js

RUN cp remotestorage.js litewrite/lib/
RUN cp remotestorage-nocache.js ghost/vendor/
RUN cp remotestorage.min.js dogfeed/vendor/remotestorage/
RUN cp remotestorage.min.js dogtalk/vendor/remotestorage/
RUN cp remotestorage-nocache.js sharesome/vendor/remotestorage/
RUN cp remotestorage.js remotestorage-browser-example/lib/
RUN cp remotestorage.js unhosted-time-tracker/libs/remote-storage/remoteStorage-debug.js
RUN cp remotestorage.min.js svg-edit/editor/extensions/ext-remotestorage/
RUN cp remotestorage.js vidmarks/vendor/remoteStorage.js
RUN cp remotestorage.js html-music-player/ext/js/
RUN cp remotestorage.js myfavoritedrinks/
RUN cp remotestorage.js todomvc/labs/architecture-examples/remotestorage/js/
RUN cp remotestorage.js dspace-client/deps/remoteStorage.js
RUN cp remotestorage.js meute/upstream/
RUN cp remotestorage.js import.5apps.com/vendor/
RUN cp remotestorage.js export.5apps.com/vendor/
RUN cp remotestorage.js store/

RUN cd litewrite ; grunt build
