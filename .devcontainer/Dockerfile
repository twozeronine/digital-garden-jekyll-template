# 베이스 이미지를 ruby 3.1으로 설정
FROM ruby:3.1

# Jekyll 설치에 필요한 패키지 설치
RUN apt-get update && apt-get install -y \
    build-essential \
    libffi-dev \
    zlib1g-dev \
    libgmp-dev \
    libssl-dev \
    && rm -rf /var/lib/apt/lists/*

# Jekyll과 Bundler 설치
RUN gem install jekyll bundler

# 작업 디렉토리 설정
WORKDIR /workspace

# 번들러 설정 (선택사항)
COPY Gemfile* ./
RUN bundle install || true

# 기본 명령어로 bash 설정
CMD [ "bash" ]
