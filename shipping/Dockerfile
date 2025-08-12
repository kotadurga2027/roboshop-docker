FROM maven
WORKDIR /opt/server
COPy pom.xml .
COPY src .
RUN mvn clean package 
RUn mv /opt/server/target/shipping-1.0.jar /opt/server/shipping.jar 
ENV CART_ENDPOINT="cart:8080" \
    DB_HOST="mysql"
CMD ["java","-jar","shipping.jar"]