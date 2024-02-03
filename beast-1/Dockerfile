FROM boost-base as beast-1

# Set working directory
WORKDIR /app

# Install required packages
RUN apt-get update && apt-get install -y \
    cmake \
    g++ \
    wget \
    libssl-dev \
    libasio-dev \
    libspdlog-dev

# Set the Boost version
ARG BOOST_VERSION=1.84.0
ARG BOOST_VERSION_UNDERSCORE=1_84_0

# Set work directory back to /app
WORKDIR /app

# Copy the source code
COPY . .

# Build the application
RUN cmake . && make

# Command to run the application
CMD ["./beast-1", "0.0.0.0", "8080", "1"]
