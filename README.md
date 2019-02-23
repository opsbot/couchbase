# couchbase

a cli client for working with couchbase api

`https://docs.couchbase.com/server/4.5/rest-api/rest-endpoints-all.html`

## supported endpoints

- [ ] GET /pools Retrieves cluster information.
- [ ] GET /pools/default Retrieves cluster details.
- [ ] POST /controller/addNode Adds nodes to clusters.
- [ ] POST /node/controller/doJoinCluster Joins nodes into clusters
- [ ] POST /controller/ejectNodeentry Removes nodes from clusters.
- [ ] GET, POST, PUT, DELETE /pools/default/serverGroups Manages rack zone awareness (server groups).
- [ ] POST /controller/rebalance Rebalances nodes in a cluster.
- [ ] GET, POST /internalSettings Manages internal settings. Couchbase Server use only.
- [ ] GET, POST /settings/maxParallelIndexers Manages parallel indexer configuration.
- [ ] GET, POST /settings/autoFailover Manages automatic failover for clusters.
- [ ] GET, POST /settings/autoFailover/resetCount Resets automatic failover for clusters.
- [ ] GET, POST /settings/alerts Manages alerts for email notifications.
- [ ] POST /settings/alerts/testEmail Creates test email for email notifications.
- [ ] POST /settings/alerts/sendTestEmail Sends test email for email notifications.
- [ ] GET /pools/nodes Retrieves information about nodes in a cluster.
- [ ] POST /controller/setRecoveryType Sets the recovery type to be performed for a node.
- [ ] POST /controller/failOver Fails over nodes.
- [ ] POST /controller/startGracefulFailover Sets graceful failover for a specific server node.
- [ ] POST /node/controller/setupServices Sets the services (data, query, index, fts).
- [ ] POST /settings/web Sets user names and passwords.
- [ ] POST /pools/default/memoryQuota The memoryQuota parameter sets the memory quota.
- [ ] POST /nodes/self/controller/settings Sets the path for index files.
- [ ] GET /pools/default/buckets/default/nodes/[host]:[port]/stats Retrieves statistics for a node.
- [ ] GET /pools/default/serverGroups Retrieves information about a server group.
- [ ] POST /pools/default/serverGroups Creates a server group with a specific name.
- [ ] PUT /pools/default/serverGroups/<:uuid> Updates the server group information.
- [ ] PUT /pools/default/serverGroups?rev=<:number> Updates a server’s group memberships.
- [ ] DELETE /pools/default/serverGroups/<:uuid> Deletes a specific server group.
- [ ] GET /pools/default/buckets Retrieves all bucket and bucket operations information from a cluster.
- [ ] GET /pools/default/buckets/default Retrieves information for a single bucket associated with a cluster.
- [ ] GET /pools/default/buckets/[bucket_name]/stats Retrieves bucket statistics for a specific bucket.
- [ ] POST /pools/default/buckets Creates a new Couchbase bucket.
- [ ] DELETE /pools/default/buckets/[bucket_name] Deletes a specific bucket.
- [ ] POST /pools/default/buckets/default/controller/doFlush Flushes a specific bucket.
- [ ] GET /pools/nodes Retrieves information about nodes in a cluster.
- [ ] POST /pools/nodes/indexMemoryQuota The indexMemoryQuota parameter sets the memory quota for the Index service.
- [ ] GET /settings/indexes Retrieves parameter settings for the Index service.
- [ ] POST /settings/indexes Sets the parameter settings for the Index service.
- [ ] GET /[bucket_name]/_design/[ddoc-name] Retrieves design documents.
- [ ] GET /[bucket_name]/_design/[ddoc-name]/_view/[view-name] Retrieves views.
- [ ] GET /[bucket-name]/_design/[ddoc-name]/_spatial/[spatial-name] Retrieves spatial views.
- [ ] PUT /[bucket_name]/_design/[ddoc-name] Creates a news design document with one or more views.
- [ ] DELETE /[bucket_name]/_design/[ddoc-name] Deletes design documents.
- [ ] POST /internalSettings Changes the number of simultaneous requests each node can accept.
- [ ] GET /pools/default/remoteClusters Retrieves the destination cluster reference
- [ ] POST /pools/default/remoteClusters Creates a reference to the destination cluster
- [ ] PUT /pools/default/remoteClusters/[UUID] Modifies the destination cluster reference
- [ ] DELETE /pools/default/remoteClusters/[UUID] Deletes the reference to the destination cluster.
- [ ] GET /pools/default/certificate Retrieves the certificate from the cluster.
- [ ] POST /controller/regenerateCertificate Regenerates a certificate on a destination cluster.
- [ ] DELETE /controller/cancelXDCR/[replication_id] Deletes the replication.
- [ ] GET, POST /settings/replications/ Global setting supplied to all replications for a cluster.
- [ ] GET, POST /settings/replications/[replication_id] Settings for a specific replication for a bucket.
- [ ] GET /pools/default/buckets/@xdcr[bucket_name]/stats/[destination_endpoint]_ Retrieves bucket statistics.
- [ ] POST /pools/default/buckets/[bucket_name]/controller/compactBucket Compacts bucket data and indexes.
- [ ] POST /pools/default/buckets/[bucket_name]/controller/cancelBucketCompaction Cancels compaction for the specified bucket.
- [ ] POST /[bucket_name]/_design/[ddoc_name]/_spatial/_compact  Compacts a spatial view.
- [ ] POST /controller/setAutoCompaction Sets cluster-wide auto-compaction intervals and thresholds
- [ ] GET /settings/autoCompaction Retrieves cluster-wide settings for auto-compaction
- [ ] GET /pools/default/buckets/[bucket_name] Retrieves auto-compaction settings for named bucket
- [ ] POST /pools/default/buckets/[bucket_name] Sets auto-compaction interval or thresholds for named bucket
- [ ] GET /diag Retrieves log and additional server diagnostic information.
- [ ] GET /sasl_logs Retrieves a generic list of log information.
- [ ] GET /sasl_logs/[log_name] Retrieves information from the specified log category. Where the log_name is one of the following log types:
- [ ] POST /logClientError Adds entries to the central log from a custom Couchbase Server SDK.
- [ ] POST /settings/readOnlyUser Creates the read-only user username, password,
- [ ] PUT /settings/readOnlyUser Changes the read-only user password
- [ ] DELETE /settings/readOnlyUser Deletes the user
- [ ] GET /settings/readOnlyAdminName Retrieves the read-only username
- [ ] GET /pools/default/certificate Returns the current cluster certificate.
- [ ] POST /controller/uploadClusterCA Uploads a pem-encoded root certificate (cluster CA) to the cluster.
- [ ] POST /node/controller/reloadCertificate Takes a certificate/key from the specified directory and applies them to the node.
- [ ] GET /pools/default/certificate/node/<host:port> Retrieves the read-only username

## environment config

create a config file in your home directory `~/.config/.couchbase.json`

```json
{
    "default": {
        "Host": "http://localhost:8000",
    },
}
```

for support of multiple configurations create additional top level elements in your config file and pass a matching `--env` flag with your commands

if no `--env` flag is passed the cli will load the `default` configuration

## load build harness

```sh
make init
```

## fetch cli dependencies

```sh
GO111MODULE=on go mod vendor
```
