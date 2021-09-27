# PowerSHellConvertfiletoUTF8NOBOM
======================================================================================

$Utf8NoBomEncoding = New-Object System.Text.UTF8Encoding($False)
$files = [IO.Directory]::GetFiles("C:\Test\NoBOM")
foreach($file in $files) 
{     write $file
   # $content = get-content –path $file
   # $content | out-file $file –encoding utf8   
   $output = Get-Content -Path $file
  # write $output
  [System.IO.File]::WriteAllLines($file, $output, $Utf8NoBomEncoding) 

}
=========================================================================
