FROM golang:1.21-alpine AS builder
WORKDIR /app
COPY  . .
RUN go build -o server .

FROM alpine:3.18.3 AS final
WORKDIR /app
COPY --from=builder /app/server .
EXPOSE 8080
CMD ["./server"]