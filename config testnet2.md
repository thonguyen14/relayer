global:
    api-listen-addr: :5183
    timeout: 300s
    memo: thonguyen#5227
    light-cache-size: 20
chains:
    GAIA:
        type: cosmos
        value:
            key: gaia-rly
            chain-id: GAIA
            rpc-addr: http://localhost:26957
            grpc-addr: http://localhost:9490
            account-prefix: cosmos
            keyring-backend: test
            gas-adjustment: 1.2
            gas-prices: 0.0025uatom
            debug: true
            timeout: 300s
            output-format: json
            sign-mode: direct
            memo-prefix: thonguyen#5227
    STRIDE-TESTNET-2:
        type: cosmos
        value:
            key: stride-rly
            chain-id: STRIDE-TESTNET-2
            rpc-addr: http://localhost:16657
            grpc-addr: http://localhost:16090
            account-prefix: stride
            keyring-backend: test
            gas-adjustment: 1.2
            gas-prices: 0.0025ustrd
            debug: true
            timeout: 300s
            output-format: json
            sign-mode: direct
            memo-prefix: thonguyen#5227
paths:
    STRIDE-GAIA:
        src:
            chain-id: GAIA
            client-id: 07-tendermint-0
            connection-id: connection-0
        dst:
            chain-id: STRIDE-TESTNET-2
            client-id: 07-tendermint-0
            connection-id: connection-0
        src-channel-filter:
            rule: "allowlist"
            channel-list: [channel-0, channel-1, channel-2, channel-3, channel-4]
