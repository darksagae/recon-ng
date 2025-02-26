# recon-ng
**Recon-ng** is a powerful web reconnaissance framework included in Kali Linux that provides a comprehensive environment for gathering and analyzing open-source intelligence (OSINT). It streamlines the process of collecting data from various sources, enabling security professionals to perform reconnaissance more effectively.

### Installation

Recon-ng is usually pre-installed in Kali Linux. To check if it's installed, you can simply run:

```bash
recon-ng
```

If it's not installed, you can install it using:

```bash
sudo apt-get install recon-ng
```

### Basic Usage

1. **Starting Recon-ng**:
   Launch Recon-ng from the terminal:

   ```bash
   recon-ng
   ```

   You will enter the interactive console.

2. **Creating a New Workspace**:
   Workspaces help organize your projects. You can create a new workspace with:

   ```bash
   workspaces create <workspace_name>
   ```

3. **Setting a Domain**:
   After creating a workspace, set the target domain you want to investigate:

   ```bash
   set domain example.com
   ```

4. **Adding Modules**:
   Recon-ng uses modules to perform various tasks. To see available modules, use:

   ```bash
   modules search
   ```

   To load a specific module, use:

   ```bash
   modules load <module_name>
   ```

5. **Running a Module**:
   After loading a module, you can run it using:

   ```bash
   run
   ```

   For example, if you load the `recon/domains-hosts/bing_domain` module, it will search for subdomains.

### Examples and Expected Output

1. **Example: Discovering Subdomains**:
   Load the Bing module to find subdomains:

   ```bash
   modules load recon/domains-hosts/bing_domain
   set domain example.com
   run
   ```

   **Expected Output**:
   ```
   +-------------------+
   | Subdomains Found  |
   +-------------------+
   | www.example.com   |
   | api.example.com   |
   | mail.example.com  |
   +-------------------+
   ```

2. **Example: Gathering WHOIS Data**:
   Load the WHOIS module to gather registration information:

   ```bash
   modules load recon/contacts/whois_pocs
   set domain example.com
   run
   ```

   **Expected Output**:
   ```
   +------------------+----------------------+
   | Name             | Email                |
   +------------------+----------------------+
   | John Doe         | john@example.com     |
   | Jane Smith       | jane@example.com     |
   +------------------+----------------------+
   ```

3. **Example: DNS Resolution**:
   Use the DNS resolution module to resolve domains:

   ```bash
   modules load recon/domains-hosts/resolve
   set domain example.com
   run
   ```

   **Expected Output**:
   ```
   +-------------------+--------------------+
   | Domain            | IP Address         |
   +-------------------+--------------------+
   | www.example.com   | 192.0.2.1          |
   | api.example.com   | 192.0.2.2          |
   +-------------------+--------------------+
   ```

### Conclusion

Recon-ng is a versatile tool for OSINT gathering, allowing users to automate and streamline their reconnaissance efforts. By utilizing its modules, security professionals can effectively gather information about their targets, which is essential for penetration testing and security assessments. Always remember to use it ethically and with permission.



                                 ALTERNATIVE
### Recon-ng: A Powerful Reconnaissance Tool

**Recon-ng** is a full-featured web reconnaissance framework written in Python. It provides a powerful environment to conduct open-source intelligence (OSINT) gathering. Recon-ng is designed to help security professionals and penetration testers collect data about targets efficiently.

### Installation

Recon-ng is often pre-installed on Kali Linux. If you need to install it, you can do so with:

```bash
sudo apt-get install recon-ng
```

### Basic Usage

To start Recon-ng, simply run the following command in your terminal:

```bash
recon-ng
```

This will open the Recon-ng console, where you can enter commands.

### Common Commands and Examples

1. **Create a New Workspace**:
   Workspaces allow you to separate different projects within Recon-ng.

   ```bash
   workspaces create example_workspace
   ```

   **Output**:
   ```
   Workspace 'example_workspace' created.
   ```

2. **Adding a Domain**:
   Add a target domain for reconnaissance.

   ```bash
   add domains example.com
   ```

   **Output**:
   ```
   Domain 'example.com' added.
   ```

3. **Listing Available Modules**:
   View available modules that can be used for gathering information.

   ```bash
   modules search
   ```

   **Output**:
   ```
   +---------------------+-------------------+-------------+
   | Name                | Description       | Type        |
   +---------------------+-------------------+-------------+
   | recon/domains-hosts | Find hosts        | discovery   |
   | recon/domains-swhois| WHOIS information | discovery   |
   | recon/hosts-ip      | IP addresses      | discovery   |
   +---------------------+-------------------+-------------+
   ```

4. **Running a Module**:
   To gather information about the domain, run a specific module.

   ```bash
   modules load recon/domains-hosts
   ```

   After loading the module, run it:

   ```bash
   run
   ```

   **Output**:
   ```
   [+] Found hosts:
   - 192.0.2.1
   - 192.0.2.2
   ```

5. **Exporting Data**:
   You can export your findings to different formats, such as CSV.

   ```bash
   export csv /path/to/output.csv
   ```

   **Output**:
   ```
   Data exported to /path/to/output.csv.
   ```

### Conclusion

Recon-ng offers a versatile platform for gathering OSINT and conducting thorough reconnaissance on target domains. Its modular approach allows users to customize their information-gathering processes effectively. Always ensure ethical practices when using such tools to gather information.




                                 ALTERNATIVE
Recon-ng is a web reconnaissance framework, not a tool specifically for network scanning like Nmap. It's a powerful tool for gathering information about a target, including domain names, IP addresses, and web servers. Here's an overview of how to use Recon-ng, along with some examples and expected output:

**Basic Usage**

To use Recon-ng, you'll need to launch it from the command line in Kali Linux:
```
recon-ng
```
This will open the Recon-ng console.

**Modules**

Recon-ng uses modules to perform specific tasks. You can list all available modules using the `modules` command:
```
recon-ng > modules
```
This will display a list of available modules, including those for domain enumeration, IP address gathering, and web server discovery.

**Examples**

1. **Domain Enumeration**

To enumerate subdomains for a target domain, use the `recon/domains-hosts/brute_hosts` module:
```
recon-ng > use recon/domains-hosts/brute_hosts
recon-ng [brute_hosts] > set DOMAIN example.com
recon-ng [brute_hosts] > run
```
Expected output:
```
+---------------+---------------+
|  Host         |  IP Address   |
+---------------+---------------+
|  example.com  |  192.0.2.1    |
|  subdomain1   |  192.0.2.2    |
|  subdomain2   |  192.0.2.3    |
+---------------+---------------+
```
2. **IP Address Gathering**

To gather IP addresses for a target domain, use the `recon/hosts/host` module:
```
recon-ng > use recon/hosts/host
recon-ng [host] > set DOMAIN example.com
recon-ng [host] > run
```
Expected output:
```
+---------------+---------------+
|  IP Address   |  Host         |
+---------------+---------------+
|  192.0.2.1    |  example.com  |
|  192.0.2.2    |  subdomain1  |
|  192.0.2.3    |  subdomain2  |
+---------------+---------------+
```
3. **Web Server Discovery**

To discover web servers for a target IP address, use the `recon/net/web/web_server` module:
```
recon-ng > use recon/net/web/web_server
recon-ng [web_server] > set RHOSTS 192.0.2.1
recon-ng [web_server] > run
```
Expected output:
```
+---------------+---------------+
|  URL          |  Server       |
+---------------+---------------+
|  http://example.com  |  Apache/2.4.29 |
|  https://example.com |  Apache/2.4.29 |
+---------------+---------------+
```
These are just a few examples of what Recon-ng can do. With its modular design and extensive library of modules, Recon-ng is a powerful tool for web reconnaissance.




                                     ALTERNATIVE
Recon-ng is a powerful, open-source reconnaissance framework designed for web-based information gathering. It's written in Python and aims to automate the process of collecting information about targets. Unlike Nmap, which focuses on network scanning, recon-ng specializes in gathering intelligence from various online sources.

### Basic Usage

1.  **Installation:** Recon-ng is usually pre-installed on Kali Linux. If not, you can install it using:

    ```bash
    sudo apt-get install recon-ng
    ```

2.  **Starting Recon-ng:** To start the framework, simply type `recon-ng` in the terminal.

    ```bash
    recon-ng
    ```

3.  **Workspace Management:** Recon-ng uses workspaces to organize different projects.

    *   To create a new workspace:

    ```
    workspaces create <workspace_name>
    ```

    *   To load an existing workspace:

    ```
    workspaces load <workspace_name>
    ```

4.  **Modules:** Recon-ng utilizes modules to perform various tasks.

    *   To list available modules:

    ```
    modules search
    ```

    *   To load a specific module:

    ```
    modules load <module_name>
    ```

    *   To show information about a module:

    ```
    modules info <module_name>
    ```

    *   To set options for a module:

    ```
    options set <option_name> <value>
    ```

    *   To execute a module:

    ```
    run
    ```

### Examples and Output

Here are a few examples of how to use recon-ng with common modules:

1.  **Using the `hackertarget` module to find hosts:**

    *   Load the module:

    ```
    modules load hackertarget
    ```

    *   Set the `SOURCE` option to the target domain:

    ```
    options set SOURCE example.com
    ```

    *   Run the module:

    ```
    run
    ```

    *   **Expected Output:** This module queries the hackertarget.com API to find hosts associated with the domain `example.com`. The output will be a list of subdomains and IP addresses, which are stored in the `hosts` table within the recon-ng database.

2.  **Using the `bing_domain_web` module to discover subdomains:**

    *   Load the module:

    ```
    modules load bing_domain_web
    ```

    *   Set the `SOURCE` option to the target domain:

    ```
    options set SOURCE example.com
    ```

    *   Run the module:

    ```
    run
    ```

    *   **Expected Output:** This module uses the Bing search engine to find subdomains of `example.com`. It populates the `hosts` table with any discovered subdomains.

3.  **Using the `theharvester` module for email harvesting:**

    *   Load the module:

    ```
    modules load theharvester
    ```

    *   Set the `SOURCE` option to the target domain:

    ```
    options set SOURCE example.com
    ```

    *   Run the module:

    ```
    run
    ```

    *   **Expected Output:** This module uses theHarvester tool to find email addresses associated with `example.com` from various search engines and sources. The results are stored in the `contacts` table.

4.  **Reporting:** To view the data collected, you can query the recon-ng database.

    *   To show all hosts:

    ```
    show hosts
    ```

    *   To show all contacts:

    ```
    show contacts
    ```

    *   **Expected Output:** These commands will display tables of the data collected by the modules, such as hostnames, IP addresses, email addresses, and other information.

5.  **Generating Reports:** Recon-ng also allows you to generate reports in various formats.

    *   To generate a report:

    ```
    spool <filename.txt>
    ```

    Run the modules and `show` commands you want to include in the report.

    ```
    spool off
    ```

### Key Features and Considerations

*   **Modularity:** Recon-ng's modular design makes it easy to extend its functionality.
*   **Database Integration:** It stores collected data in a database, allowing for easy querying and reporting.
*   **API Keys:** Many modules require API keys from services like Shodan, VirusTotal, or Bing. You'll need to obtain these keys and set them as options for the respective modules.
*   **Ethical Use:** As with any reconnaissance tool, use recon-ng responsibly and ethically. Only gather information on targets for which you have explicit permission.




                                          ALTERNATIVE
Recon-ng is a powerful open-source reconnaissance tool included in Kali Linux, designed for gathering open-source intelligence (OSINT). It provides a modular framework that allows users to collect and analyze information about targets efficiently. Here’s how to use Recon-ng, along with examples and expected outputs.

### Installation

Recon-ng is typically pre-installed in Kali Linux. However, to ensure you have the latest version, you can run the following command:

```bash
sudo apt-get update && sudo apt-get install recon-ng
```

If you are using another Linux distribution, you can clone it from GitHub and install the required dependencies:

```bash
git clone https://github.com/lanmaster53/recon-ng.git
cd recon-ng
pip install -r REQUIREMENTS
```

### Starting Recon-ng

To start Recon-ng, simply type:

```bash
recon-ng
```

This will launch the interactive console where you can begin your reconnaissance tasks.

### Basic Usage

1. **Creating a Workspace**:
   Workspaces help organize your data. To create a new workspace, use:

   ```bash
   workspaces create example_name
   ```

   You can switch to this workspace with:

   ```bash
   recon-ng -w example_name
   ```

2. **Listing Available Modules**:
   Recon-ng has various modules for different tasks. To see available modules, use:

   ```bash
   marketplace search
   ```

   This command will display a list of modules along with their status (installed or not) and other details.

3. **Installing a Module**:
   To install a specific module, use:

   ```bash
   marketplace install <module_name>
   ```

   For example, to install a module for reverse WHOIS lookups:

   ```bash
   marketplace install recon/companies-domains/viewdns_reverse_whois
   ```

4. **Loading a Module**:
   After installing a module, you need to load it to use it:

   ```bash
   modules load recon/companies-domains/viewdns_reverse_whois
   ```

5. **Setting Options**:
   Before running a module, you often need to set options, such as the target domain:

   ```bash
   options set SOURCE example.com
   ```

6. **Running the Module**:
   Finally, execute the module with:

   ```bash
   run
   ```

### Example Output

When you run a module like `viewdns_reverse_whois`, the output might look like this:

```
[*] Querying for reverse WHOIS information on example.com...
[*] Found 5 records:
1. example1@example.com
2. example2@example.com
3. example3@example.com
4. example4@example.com
5. example5@example.com
```

This output indicates that the module successfully retrieved reverse WHOIS information related to the specified domain.

### Conclusion

Recon-ng is a versatile tool for OSINT that allows users to gather and analyze data efficiently. Its modular design and interactive console make it user-friendly for both beginners and experienced security professionals.

---
Learn more:
1. [Recon-NG Tutorial | HackerTarget.com](https://hackertarget.com/recon-ng-tutorial/)
2. [Recon-ng Information gathering tool in Kali Linux - GeeksforGeeks](https://www.geeksforgeeks.org/recon-ng-installation-on-kali-linux/)
3. [recon-ng | Kali Linux Tools](https://www.kali.org/tools/recon-ng/)  
