# Data

**Dataset**: NSL-KDD–A refined version of the KDD Cup 1999 dataset for network intrusion detection research.  
It contains simulated network traffic instances labeled as either *normal* or various types of attacks.  
The dataset is widely used for evaluating intrusion detection systems and anomaly detection methods.

# Codebook for NSL-KDD Dataset

## Variable Names, Data Types, and Descriptions

| Column Name | Data Type | Description |
|---------------|---------------|-------------------------------------------|
| `duration` | int64 | Length (in seconds) of the connection. |
| `protocol_type` | object | Protocol used (e.g., tcp, udp, icmp). |
| `service` | object | Network service on the destination (e.g., http, telnet). |
| `flag` | object | Status flag of the connection. |
| `src_bytes` | int64 | Number of data bytes sent from source to destination. |
| `dst_bytes` | int64 | Number of data bytes sent from destination to source. |
| `land` | int64 | 1 if connection is from/to the same host/port; 0 otherwise. |
| `wrong_fragment` | int64 | Number of wrong fragments. |
| `urgent` | int64 | Number of urgent packets. |
| `hot` | int64 | Number of "hot" indicators. |
| `num_failed_logins` | int64 | Number of failed login attempts. |
| `logged_in` | int64 | 1 if successfully logged in; 0 otherwise. |
| `num_compromised` | int64 | Number of compromised conditions. |
| `root_shell` | int64 | 1 if root shell is obtained; 0 otherwise. |
| `su_attempted` | int64 | 1 if "su root" command attempted; 0 otherwise. |
| `num_root` | int64 | Number of "root" accesses. |
| `num_file_creations` | int64 | Number of file creation operations. |
| `num_shells` | int64 | Number of shell prompts invoked. |
| `num_access_files` | int64 | Number of accesses to control files. |
| `num_outbound_cmds` | int64 | Number of outbound commands (always 0 in KDD99). |
| `is_host_login` | int64 | 1 if login is to a host account; 0 otherwise. |
| `is_guest_login` | int64 | 1 if login is to a guest account; 0 otherwise. |
| `count` | int64 | Number of connections to the same host in the past 2 seconds. |
| `srv_count` | int64 | Number of connections to the same service in the past 2 seconds. |
| `serror_rate` | float64 | % of connections with SYN errors. |
| `srv_serror_rate` | float64 | % of connections to the same service with SYN errors. |
| `rerror_rate` | float64 | % of connections with REJ errors. |
| `srv_rerror_rate` | float64 | % of connections to the same service with REJ errors. |
| `same_srv_rate` | float64 | % of connections to the same service. |
| `diff_srv_rate` | float64 | % of connections to different services. |
| `srv_diff_host_rate` | float64 | % of connections to different hosts on the same service. |
| `dst_host_count` | int64 | Number of connections to the destination host. |
| `dst_host_srv_count` | int64 | Number of connections to the destination host and service. |
| `dst_host_same_srv_rate` | float64 | % of connections to the same service on the destination host. |
| `dst_host_diff_srv_rate` | float64 | % of connections to different services on the destination host. |
| `dst_host_same_src_port_rate` | float64 | % of connections from the same source port. |
| `dst_host_srv_diff_host_rate` | float64 | % of connections to the same service from different hosts. |
| `dst_host_serror_rate` | float64 | % of connections with SYN errors to the destination host. |
| `dst_host_srv_serror_rate` | float64 | % of connections with SYN errors to the destination service. |
| `dst_host_rerror_rate` | float64 | % of connections with REJ errors to the destination host. |
| `dst_host_srv_rerror_rate` | float64 | % of connections with REJ errors to the destination service. |
| `attack` | object | Label indicating the type of attack or "normal". |
| `level` | int64 | Severity or confidence score of the attack (if available). |


### This is the post-EDA and preprocessing dataset

| Column Name | Data Type | Description |
|-------------|-----------|-------------|
| `src_bytes` | float64 | Number of data bytes sent from source to destination. |
| `dst_bytes` | float64 | Number of data bytes sent from destination to source. |
| `diff_srv_rate` | float64 | % of connections to different services. |
| `same_srv_rate` | float64 | % of connections to the same service. |
| `dst_host_srv_count` | float64 | Number of connections to the same service on the destination host. |
| `flag_SF` | float64 | 1 if the connection ended normally (SYN flag), 0 otherwise. |
| `dst_host_same_srv_rate` | float64 | % of connections to the same service on the destination host. |
| `dst_host_diff_srv_rate` | float64 | % of connections to different services on the destination host. |
| `logged_in` | float64 | 1 if successfully logged in; 0 otherwise. |
| `serror_rate` | float64 | % of connections with SYN errors. |
| `count` | float64 | Number of connections to the same host in the past 2 seconds. |
| `dst_host_srv_diff_host_rate` | float64 | % of connections to the same service from different hosts. |
| `service_http` | float64 | 1 if the service is HTTP; 0 otherwise (one-hot encoded). |
| `dst_host_count` | float64 | Number of connections to the destination host. |
| `dst_host_same_src_port_rate` | float64 | % of connections from the same source port. |
| `service_private` | float64 | 1 if the service is a “private” port; 0 otherwise (one-hot encoded). |
| `srv_diff_host_rate` | float64 | % of connections to different hosts on the same service. |
| `is_anomalous` | int64 | Binary target: 1 = attack (anomalous), 0 = normal. |

It includes 17 features and the target.

## Data Types

All data types are listed in the table above alongside their descriptions.
