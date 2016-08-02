splunkforwarder
=========

Install and configure Splunkforwarder on RHEL-systems.

Requirements
------------
none.

Role Variables
--------------
- Index-server:
  - ```splunkforwarder_server: '127.0.0.1:9997'```
- Default install-directory: 
  - ```splunkforwarder_dir: '/opt/splunkforwarder/'```
- IP-Address to listen on: 
  - ```frontend_ip: 127.0.0.1```

- List of to be indexed logfiles on all/most hosts to use in group_vars
```
- splunkforwarder_log_items:
  - app_name: custom
    source: "/var/log/messages"
    index: "syslog"
    sourcetype: linux_messages_syslog
```

- List of custom to be indexed logfiles to use in host_vars
```
 - splunkforwarder_log_items_custom:
   - app_name: custom
     source: "/var/log/mysql.log"
     index: "mysql"
     sourcetype: mysql```
```
Dependencies
------------
none.

Example Playbook
----------------
```
- hosts: all
  gather_facts: true
  roles:
  - role: splunkforwarder
```

License
-------
See LICENSE

Author Information
------------------

Author: Sebastian Gumprich

Author: [T-Systems Multimedia Solutions GmbH](http://www.t-systems-mms.com/)


Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.
