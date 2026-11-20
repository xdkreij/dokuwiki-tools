==== Ansible ====

== dokuwiki_inventory_gen.yml ==
*requires*
- a running dokuwiki in a container
- foreman/satellite to gather kernel information

*What this playbook does*
- it gathers all facts from your hosts
- it gathers latest kernel release from your foreman/satellite system
- it generates a live asset page
   - it returns a table with
      FQDN 	Role 	Owner 	Operating system 	Kernel 	Uptime 	IPv4 	MAC 	vCPUs 	Memory (GiB) 
      
- it generates sub asset pages - one per vm - with links on the main live asset page
  - it returns multiple tables with basic system facts, application services, Network and Filesystem

*what to change prior to using the playbook*
- ensure your host groups in both tasks in the main playbook are set
   - first is for facts gathering
   - second is the dokuwiki host fqdn
- ensure to include the /data/path/to/your/wiki/pages on the dokuwiki VM
- ensure the required variables are set in your own inventory 
   see defaults/dokuwiki_inventory_gen.yml
