# Build stage
FROM golang:1.19.5 AS build

WORKDIR /app
COPY main.go ./
RUN go build -o main main.go

# Run stage
FROM scratch

WORKDIR /app
COPY --from=build /app/main ./

CMD ["./main"]