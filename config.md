global:
    api-listen-addr: :5183
    timeout: 300s
    memo: thonguyen#5227
    light-cache-size: 20
chains:
    GAIA:
        type: cosmos
        value:
            key: gaia207
            chain-id: GAIA
            rpc-addr: http://138.201.139.207:21657
            grpc-addr: http://138.201.139.207:1090
            account-prefix: cosmos
            keyring-backend: test
            gas-adjustment: 1.2
            gas-prices: 0.0025uatom
            debug: true
            timeout: 300s
            output-format: json
            sign-mode: direct
            memo-prefix: thonguyen#5227
    STRIDE-TESTNET-4:
        type: cosmos
        value:
            key: stride183
            chain-id: STRIDE-TESTNET-4
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
            chain-id: STRIDE-TESTNET-4
            client-id: 07-tendermint-0
            connection-id: connection-0
        src-channel-filter:
            rule: "allowlist"
            channel-list: [channel-0, channel-1, channel-2, channel-3, channel-4]
