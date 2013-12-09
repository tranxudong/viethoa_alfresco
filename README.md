viethoa_alfresco
================
Để Việt hóa Alfresco, phải dịch các file .property thủ công. Các property được đặt ở thư mục <custom config>/messages và có định dạng _XX_YY.properties.
Tomcat – <Tomcat home>/shared/classes/alfresco (for example, C:\alfresco\tomcat\shared\classes\alfresco)
JBoss – <JBoss home>/server/default/conf/alfresco (for example, C:\alfresco\jboss\server\default\conf\alfresco)
Hoặc đóng gói file *.jar rồi copy vào 
Tomcat – <Tomcat home>/shared/lib (for example, C:\alfresco\tomcat\shared\lib)
JBoss – <JBoss home>/server/default/conf/lib (for example, C:\alfresco\jboss\server\default\conf\lib)
Để thay đổi các tùy chọn ngôn ngữ khi đăng nhập, phải chỉnh sửa file web-client-config-custom (có thể đổi tên của file sample):
File ‘web-client-config-custom.xml’ nằm trong thư mục <custom config>/extension
Tìm ‘<languages>’ section
Thêm hay xóa ngôn ngữ theo định dạng:  ‘<language locale=”XX_YY”>LangName</language>’
Save file sau khi sửa
<!--
   <config evaluator="string-compare" condition="Languages">
     <languages>
        <language locale="fr_FR">French</language>
        <language locale="de_DE">German</language>
        <language locale="ja_JP">Japanese</language>
     </languages>
   </config>
  -->

Để dịch các field trong file property có thể dùng tool sau:
http://sourceforge.net/projects/alfresco
hay download trực tiếp
http://sourceforge.net/project/showfile ... _id=162536

Lưu ý khi sử dụng tiếng Việt trong file property phải sử dụng công cụ native2ascii để chuyển đổi UTF8 sang ascii.
Các file property nên download ở language package section trên website alfresco sourceforge.
Sau khi cập nhật phải restart lại server alfresco để thay đổi có hiệu lực.
Các file property:
-webclient: chứa các title login, giao diện web,...
