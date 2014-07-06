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

# prepare sharesome
RUN echo 2
RUN git clone https://github.com/apptorrent/sharesome.git
RUN cd sharesome ; git remote add 5apps git@5apps.com:michiel_sharesome-michiel.git
#RUN cp remotestorage-nocache.js sharesome/vendor/remotestorage/

# build sharesome
RUN cd sharesome ; bundle install
RUN cd sharesome ; npm install
RUN cd sharesome ; bower install --allow-root --yes
RUN cd sharesome ; grunt dist --force
RUN cd sharesome ; grunt buildcontrol:production --force
RUN cd sharesome/dist ; git remote add 5apps git@5apps.com:michiel_sharesome-michiel.git
RUN cd sharesome/dist ; git add *
RUN cd sharesome/dist ; git commit -am"build"

# prepare music player
RUN git clone https://github.com/michielbdejong/html-music-player.git
RUN cd html-music-player ; git remote add 5apps git@5apps.com:michiel_music.git
RUN cp remotestorage.js html-music-player/ext/js/

# prepare myfavoritedrinks
RUN git clone https://github.com/remotestorage/myfavoritedrinks.git
RUN cd myfavoritedrinks ; git remote add 5apps git@5apps.com:xmartin_myfavoritedrinks.git
RUN cp remotestorage.js myfavoritedrinks/

# prepare todomvc
RUN git clone https://github.com/michielbdejong/todomvc.git
RUN cd todomvc ; git remote add 5apps git@5apps.com:michiel_todomvc.git
RUN cp remotestorage.js todomvc/labs/architecture-examples/remotestorage/js/

# prepare meute
RUN git clone https://github.com/michielbdejong/meute.git
RUN cd meute ; git remote add 5apps git@5apps.com:michiel_august.git
RUN cp remotestorage.js meute/upstream/

# prepare export
RUN git clone https://github.com/michielbdejong/export.5apps.com.git
RUN cd export.5apps.com ; git remote add 5apps git@5apps.com:michiel_export.git
RUN cp remotestorage.js export.5apps.com/vendor/

# prepare import
RUN git clone https://github.com/michielbdejong/import.5apps.com.git
RUN cd import.5apps.com ; git remote add 5apps git@5apps.com:michiel_import.git
RUN cp remotestorage.js import.5apps.com/vendor/

# prepare store
RUN git clone https://github.com/unhosted/store.git
RUN cd store ; git remote add 5apps git@5apps.com:michiel_store.git
RUN cp remotestorage.js store/

# set up starter-kit
RUN git clone https://github.com/remotestorage/starter-kit.git
RUN cd starter-kit && npm install
RUN ln -s litewrite starter-kit/apps/litewrite
RUN ln -s ghost starter-kit/apps/ghost
RUN ln -s dogfeed starter-kit/apps/dogfeed
RUN ln -s dogtalk starter-kit/apps/dogtalk
RUN ln -s sharesome starter-kit/apps/sharesome
RUN ln -s html-music-player starter-kit/apps/html-music-player
RUN ln -s myfavoritedrinks starter-kit/apps/myfavoritedrinks
RUN ln -s todomvc starter-kit/apps/todomvc
RUN ln -s meute starter-kit/apps/meute
RUN ln -s export.5apps.com starter-kit/apps/export.5apps.com
RUN ln -s import.5apps.com starter-kit/apps/import.5apps.com

#
#
#
#
#
#
#
## prepare grouptabs
#RUN git clone https://github.com/xMartin/grouptabs.git
#RUN cd grouptabs ; git remote add 5apps git@5apps.com:michiel_grouptabs.git
#
## prepare browser
#RUN git clone https://github.com/nilclass/remotestorage-browser-example.git
#RUN cd remotestorage-browser-example ; git remote add 5apps git@5apps.com:michiel_browser-michiel.git
#RUN cp remotestorage.js remotestorage-browser-example/lib/
#
## prepare time tracker
#RUN git clone https://github.com/shybyte/unhosted-time-tracker.git
#RUN cd unhosted-time-tracker ; git remote add 5apps git@5apps.com:michiel_unhosted-time-tracker.git
#RUN cp remotestorage.js unhosted-time-tracker/libs/remote-storage/remoteStorage-debug.js
#
## prepare svg-edit
#RUN git clone https://github.com/nilclass/svg-edit.git
#RUN cd svg-edit ; git remote add 5apps git@5apps.com:michiel_svg-edit.git
#RUN cp remotestorage.min.js svg-edit/editor/extensions/ext-remotestorage/
#
## prepare vidmarks
#RUN git clone https://github.com/silverbucket/vidmarks.git
#RUN cd vidmarks ; git remote add 5apps git@5apps.com:michiel_vidmarks.git
#RUN cp remotestorage.js vidmarks/vendor/remoteStorage.js
#

## prepare dspace-client
#RUN git clone https://github.com/nilclass/dspace-client.git
#RUN cd dspace-client ; git remote add 5apps git@5apps.com:michiel_dspace-client-michiel.git
#RUN cp remotestorage.js dspace-client/deps/remoteStorage.js

## prepare strut
#RUN git clone https://github.com/tantaman/strut.git
#RUN #cd  ; git remote add 5apps git@5apps.com/tantaman/strut.git
