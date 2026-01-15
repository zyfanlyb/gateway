# 基于 JRE 17 运行 JAR 包
FROM eclipse-temurin:17-jre-alpine

WORKDIR /app

# 创建非 root 用户
RUN addgroup -S spring && adduser -S spring -G spring

# 复制 JAR 包（构建时从本地复制）
COPY *.jar app.jar

# 修改文件所有者
RUN chown spring:spring app.jar

USER spring:spring

# 暴露端口
EXPOSE 11001

# 启动应用
ENTRYPOINT ["java", "-jar", "app.jar"]
