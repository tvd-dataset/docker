#
# The MIT License (MIT)
#
# Copyright (c) 2013-2015 CNRS
#
# Permission is hereby granted, free of charge, to any person obtaining a copy
# of this software and associated documentation files (the "Software"), to deal
# in the Software without restriction, including without limitation the rights
# to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
# copies of the Software, and to permit persons to whom the Software is
# furnished to do so, subject to the following conditions:
#
# The above copyright notice and this permission notice shall be included in
# all copies or substantial portions of the Software.
#
# THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
# IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
# FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
# AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
# LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
# OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
# SOFTWARE.
#
# AUTHORS
# Hervé BREDIN -- http://herve.niderb.fr/

FROM ubuntu:14.04
MAINTAINER Herve Bredin (http://herve.niderb.fr)

RUN apt-get update
RUN apt-get -y install wget software-properties-common curl

# add libdvdcss-dev repository
RUN echo "# VideoLAN repository (libdvdcss)" >> /etc/apt/sources.list
RUN echo "deb http://download.videolan.org/pub/debian/stable/ /" >> /etc/apt/sources.list
RUN echo "deb-src http://download.videolan.org/pub/debian/stable/ /" >> /etc/apt/sources.list
RUN wget -O - http://download.videolan.org/pub/debian/videolan-apt.asc|apt-key add -

# add vobsub2srt repository
RUN echo "# vobsub2srt repository" >> /etc/apt/sources.list
RUN echo "deb http://ppa.launchpad.net/ruediger-c-plusplus/vobsub2srt/ubuntu raring main" >> /etc/apt/sources.list
RUN echo "deb-src http://ppa.launchpad.net/ruediger-c-plusplus/vobsub2srt/ubuntu raring main" >> /etc/apt/sources.list

# update package list
RUN apt-get -y update

# vobcopy: dvd dump
# lsdvd: dvd listing
# handbrake: dvd rip
# libav-tools + libavcodec-extra: video conversion
# samplerate-programs: audio conversion
# mencoder: extract vobsub
# vobsub2srt: OCR on vobsub
RUN apt-get -y install libdvdcss-dev vobcopy lsdvd handbrake-cli libav-tools libavcodec-extra samplerate-programs mencoder
RUN apt-get -y --force-yes install vobsub2srt

# python stuff
RUN apt-get -y install python3 python3-pip python3-dev libxml2-dev libxslt1-dev zlib1g-dev gfortran

# download tesseract data in several language
ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.ces.tar.gz /tmp/ces.tar.gz
ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.dan.tar.gz /tmp/dan.tar.gz
ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.deu.tar.gz /tmp/deu.tar.gz
ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.ell.tar.gz /tmp/ell.tar.gz
ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.eng.tar.gz /tmp/eng.tar.gz
ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.fin.tar.gz /tmp/fin.tar.gz
ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.fra.tar.gz /tmp/fra.tar.gz
ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.heb.tar.gz /tmp/heb.tar.gz
ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.hrv.tar.gz /tmp/hrv.tar.gz
ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.hun.tar.gz /tmp/hun.tar.gz
ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.nld.tar.gz /tmp/nld.tar.gz
ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.nor.tar.gz /tmp/nor.tar.gz
ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.pol.tar.gz /tmp/pol.tar.gz
ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.por.tar.gz /tmp/por.tar.gz
ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.ron.tar.gz /tmp/ron.tar.gz
ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.slv.tar.gz /tmp/slv.tar.gz
ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.spa.tar.gz /tmp/spa.tar.gz
ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.srp.tar.gz /tmp/srp.tar.gz
ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.swe.tar.gz /tmp/swe.tar.gz
ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.tur.tar.gz /tmp/tur.tar.gz
# ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.afr.tar.gz /tmp/afr.tar.gz
# ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.ara.tar.gz /tmp/ara.tar.gz
# ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.aze.tar.gz /tmp/aze.tar.gz
# ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.bel.tar.gz /tmp/bel.tar.gz
# ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.ben.tar.gz /tmp/ben.tar.gz
# ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.bul.tar.gz /tmp/bul.tar.gz
# ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.cat.tar.gz /tmp/cat.tar.gz
# ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.chi_sim.tar.gz /tmp/chi_sim.tar.gz
# ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.chi_tra.tar.gz /tmp/chi_tra.tar.gz
# ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.chr.tar.gz /tmp/chr.tar.gz
# ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.enm.tar.gz /tmp/enm.tar.gz
# ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.epo.tar.gz /tmp/epo.tar.gz
# ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.epo_alt.tar.gz /tmp/epo_alt.tar.gz
# ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.equ.tar.gz /tmp/equ.tar.gz
# ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.est.tar.gz /tmp/est.tar.gz
# ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.eus.tar.gz /tmp/eus.tar.gz
# ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.frk.tar.gz /tmp/frk.tar.gz
# ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.frm.tar.gz /tmp/frm.tar.gz
# ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.glg.tar.gz /tmp/glg.tar.gz
# ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.grc.tar.gz /tmp/grc.tar.gz
# ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.hin.tar.gz /tmp/hin.tar.gz
# ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.ind.tar.gz /tmp/ind.tar.gz
# ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.isl.tar.gz /tmp/isl.tar.gz
# ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.ita.tar.gz /tmp/ita.tar.gz
# ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.jpn.tar.gz /tmp/jpn.tar.gz
# ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.kan.tar.gz /tmp/kan.tar.gz
# ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.kor.tar.gz /tmp/kor.tar.gz
# ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.lav.tar.gz /tmp/lav.tar.gz
# ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.lit.tar.gz /tmp/lit.tar.gz
# ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.mal.tar.gz /tmp/mal.tar.gz
# ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.mkd.tar.gz /tmp/mkd.tar.gz
# ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.mlt.tar.gz /tmp/mlt.tar.gz
# ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.msa.tar.gz /tmp/msa.tar.gz
# ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.rus.tar.gz /tmp/rus.tar.gz
# ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.slk.tar.gz /tmp/slk.tar.gz
# ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.sqi.tar.gz /tmp/sqi.tar.gz
# ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.swa.tar.gz /tmp/swa.tar.gz
# ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.tam.tar.gz /tmp/tam.tar.gz
# ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.tel.tar.gz /tmp/tel.tar.gz
# ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.tgl.tar.gz /tmp/tgl.tar.gz
# ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.tha.tar.gz /tmp/tha.tar.gz
# ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.ukr.tar.gz /tmp/ukr.tar.gz
# ADD https://tesseract-ocr.googlecode.com/files/tesseract-ocr-3.02.vie.tar.gz /tmp/vie.tar.gz
RUN mkdir /tessdata
RUN for archive in /tmp/*.tar.gz; do tar -xzf $archive -C /tmp/; done
RUN mv /tmp/tesseract-ocr/tessdata/* /tessdata/
RUN rm -r /tmp/*.tar.gz /tmp/tesseract-ocr
