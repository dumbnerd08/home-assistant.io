```yaml
  version: '3'
  services:
    homeassistant:
      container_name: homeassistant
      image: "{{ include.image | default: site.installation.container }}:{{ include.tag | default: 'stable' }}"
      volumes:
        - /PATH_TO_YOUR_CONFIG:/config
        - /etc/localtime:/etc/localtime:ro
      restart: unless-stopped
      privileged: true
      ports:
        - "8123:8123"
```
