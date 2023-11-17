
go build -gcflags "all=-N -l"




docker exec -it clab-rdbg-srl1 bash
ip netns exec srbase-mgmt /opt/dlv --listen=:7000 --headless=true --log=true --api-version=2 exec /dbg/remotedebug



# kill dlv
docker exec -it clab-rdbg-srl1 bash -c "ps -afe | grep dlv | awk '{print \$2}' | xargs kill"