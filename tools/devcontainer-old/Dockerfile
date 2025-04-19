ARG VARIANT="12"
FROM debian:${VARIANT}-slim
ENV PERL_MM_USE_DEFAULT 1
ENV PYTHONUNBUFFERED 1
RUN apt-get -y update && export DEBIAN_FRONTEND=noninteractive && apt-get -y install \
  cpanminus \
  fonts-ipafont-gothic \
  libalgorithm-naivebayes-perl     \
  libclass-accessor-lite-perl      \
  libcryptx-perl                   \
  libdbd-csv-perl                  \
  libdbd-mysql-perl                \
  libdbi-perl                      \
  libexcel-writer-xlsx-perl        \
  libextutils-config-perl          \
  libextutils-helpers-perl         \
  libextutils-installpaths-perl    \
  libfile-bom-perl                 \
  libgraphics-colorutils-perl      \
  libgsl-dev                       \
  libjcode-perl                    \
  liblingua-sentence-perl          \
  libmecab-dev                     \
  libmodule-build-tiny-perl        \
  libnet-telnet-perl               \
  libproc-background-perl          \
  libspreadsheet-parseexcel-perl   \
  libstatistics-distributions-perl \
  libstatistics-lite-perl          \
  libtest-requires-perl            \
  libtext-csv-perl                 \
  libtext-diff-perl                \
  libunicode-escape-perl           \
  libxml-twig-perl                 \
  libxml2-dev                      \
  libyaml-perl                     \
  libfile-copy-recursive-perl      \
  mecab \
  mecab-ipadic-utf8 \
  perl-tk && \
  apt-get clean && rm -rf /var/cache/apt/archives/* /var/lib/apt/lists/*
RUN cpanm -n Lingua::JA::Regular::Unicode Statistics::ChisqIndep Spreadsheet::ParseXLSX
ENTRYPOINT ["sleep", "infinity"]
