# SmokeTCP box
FROM 281173056104.dkr.ecr.us-east-1.amazonaws.com/personal:base
MAINTAINER Joshua C. Forest "joshua@joshuacforest.com"
RUN apt-get install -qq git golang -y
WORKDIR /usr/local
RUN git clone https://github.com/CashStar/smoketcp.git
WORKDIR /usr/local/smoketcp
RUN git checkout use_flags_on_commandline
ENV GOPATH /usr/local/smoketcp
RUN go get github.com/cactus/go-statsd-client/statsd
RUN go build smoketcp.go
RUN mv /usr/local/smoketcp/smoketcp /usr/local/bin/smoketcp
COPY smoketcp_targets /etc/smoketcp_targets
ENTRYPOINT ["/usr/local/bin/smoketcp", "--debug=true"]
CMD ["--targetFile=/etc/smoketcp_targets"]
