FROM python:3.10

# Install MkDocs and required plugins
RUN pip install mkdocs mkdocs-material plantuml-markdown pymdown-extensions

# Install dependencies
RUN apt-get update && apt-get install -y openjdk-11-jre curl graphviz && apt-get clean

# Define PlantUML version
ENV PLANTUML_VERSION=1.2023.11

# Download specific PlantUML version
RUN curl -L "https://github.com/plantuml/plantuml/releases/download/v${PLANTUML_VERSION}/plantuml-${PLANTUML_VERSION}.jar" -o /usr/local/bin/plantuml.jar

# Create a wrapper script to run PlantUML
RUN echo '#!/bin/sh\nexec java -jar /usr/local/bin/plantuml.jar "$@"' > /usr/local/bin/plantuml && chmod +x /usr/local/bin/plantuml

WORKDIR /docs

CMD ["mkdocs", "serve", "-a", "0.0.0.0:8000"]
