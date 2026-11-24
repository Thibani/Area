FROM ghcr.io/cirruslabs/flutter:stable
WORKDIR /app
COPY pubspec.* ./
RUN flutter pub get
COPY . .
RUN flutter build apk --release
CMD ["sh", "-c", "cp build/app/outputs/flutter-apk/app-release.apk /apk/client.apk"]
