FROM golang:1.16 AS build

COPY stdoutsub /go/src/stdoutsub
WORKDIR /go/src/stdoutsub
RUN ["go", "build", "-ldflags", "-linkmode external -extldflags -static"]

FROM scratch
COPY --from=build /go/src/stdoutsub /
ENTRYPOINT ["/stdoutsub"]
