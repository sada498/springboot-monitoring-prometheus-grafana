# springboot-monitoring-prometheus-grafana

### 1.all your actuator endpoints can be accessed without requiring authentication.
    management.endpoints.web.exposure.include=*

# Micrometer
#### > Micrometer came to be. It exposes Actuator metrics to external monitoring systems such as Prometheus, Netflix Atlas, AWS Cloudwatch.
> Micrometer automatically exposes ```/actuator/metrics ```  data into something your monitoring system can understand

#### Micrometer is a separate open-sourced project
    <dependency>
    <groupId>io.micrometer</groupId>
    <artifactId>micrometer-registry-prometheus</artifactId>
    </dependency>
## Docker 
### 1. Start the docker 
### 2. Configure the ```prometheus.yml``` file
    global:
    scrape_interval: 10s
    
    scrape_configs:
    - job_name: 'spring_micrometer'
      metrics_path: '/actuator/prometheus'
      scrape_interval: 5s
      static_configs:
        - targets: ['192.168.15.7:8080']

**Note: Replace ``` 192.168.15.7``` with your localhost IP address ``` ipconfig``` to find your Ip**
### 3. Run the docker prometheus image locally
    docker run -d -p 9090:9090 -v C:/Users/X270/OneDrive/Java/springboot-monitoring-prometheus-grafana/prometheus.yml:/etc/prometheus/prometheus.yml prom/prometheus
### 4. Check your docker prometheus container ``` docker ps```
![]()
> ERROR solution while starting docker 

![]() 
![]()



 

 
