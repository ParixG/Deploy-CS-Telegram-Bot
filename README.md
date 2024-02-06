# C#-Telegram-Bot

# 1. Prepare Your C# Bot:

<b>1. Update Server:</b>

<pre><code>sudo apt update && sudo apt upgarde -y</code></pre>

<b>2. Install .NET Core:</b>

<pre><code>sudo apt install dotnet-sdk-6.0</code></pre>

# 2. Set Up MySQL Database:

<b>1. Install MySQL Server:</b>

<pre><code>sudo apt install mysql-server</code></pre>

<b>2. Secure MySQL Installation:</b>

<pre><code>sudo mysql_secure_installation</code></pre>

<b>3. Create a MySQL Database and User:</b>

<pre><code>sudo mysql -u root -p</code></pre>
<pre><code>CREATE DATABASE your_database_name;
CREATE USER 'your_username'@'localhost' IDENTIFIED BY 'your_password';
GRANT ALL PRIVILEGES ON your_database_name.* TO 'your_username'@'localhost';
FLUSH PRIVILEGES;
EXIT;</code></pre>

<b>4. Use the Database:</b>

<pre><code>USE your_database_name;</code></pre>

<b>5. Source the SQL File:</b>

<pre><code>SOURCE /path/to/your_file.sql;</code></pre>

<b>6. Verify the Import:</b>

<pre><code>SHOW TABLES;</code></pre>

<b>7. Install MySQL Connector:</b>

<pre><code>sudo apt-get install libmysqlclient-dev
dotnet add package MySql.Data</code></pre>

# 3. Set Up phpMyAdmin:

<b>1. Install Apache and PHP:</b>

<pre><code>sudo apt install apache2 php libapache2-mod-php php-mysql</code></pre>

<b>2. Install phpMyAdmin:</b>

<pre><code>sudo apt install phpmyadmin</code></pre>

<b>3. Configure Apache for phpMyAdmin:</b>

<pre><code>sudo ln -s /etc/phpmyadmin/apache.conf /etc/apache2/conf-available/phpmyadmin.conf
sudo a2enconf phpmyadmin.conf
sudo systemctl restart apache2</code></pre>

<b>4. Access phpMyAdmin in the Browser:</b>

`http://your-server-ip/phpmyadmin`

# 4. Configure Your C# Bot:

<pre><code>// Example connection string
string connectionString = "Server=localhost;Database=your_database_name;User Id=your_username;Password=your_password;";</code></pre>

# 5. Run Your C# Bot:

<pre><code>cd /path/to/publish
dotnet run project.csproj</code></pre>

# 6. Set Up as a Service (Optional):

<b>1. Create a service file:</b>

<pre><code>sudo nano /etc/systemd/system/your_bot_name.service</code></pre>

<b>2. Add the following content (adjust paths and parameters accordingly):</b>

<pre><code>[Unit]
Description=Your Bot Service

[Service]
WorkingDirectory=/path/to/publish
ExecStart=/usr/bin/dotnet your_bot_name.dll
Restart=always
RestartSec=10
SyslogIdentifier=your_bot_name
User=your_username
Environment=ASPNETCORE_ENVIRONMENT=Production

[Install]
WantedBy=multi-user.target
</code></pre>

<b>3. Save the file and enable the service:</b>

<pre><code>sudo systemctl enable your_bot_name
sudo systemctl start your_bot_name
</code></pre>







