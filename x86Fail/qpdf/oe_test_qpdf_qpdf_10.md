### oe_test_qpdf_qpdf_01：测试套编写错误

riscv与x86报错均相同

对应报错log如下

```
+ qpdf --json-help
+ grep 'json block'
+ CHECK_RESULT 1 0 0 'qpdf --json-help running failed'
```

实际使用qpdf --json-help时出现以下结果

```
[root@openeuler-riscv64 ~]# qpdf --json-help
{
  "acroform": {
    "fields": [
      {
        "alternativename": "alternative name of field -- this is the one usually shown to users",
        "annotation": {
          "annotationflags": "annotation flags from /F -- see pdf_annotation_flag_e in qpdf/Constants.h",
          "appearancestate": "appearance state -- can be used to determine value for checkboxes and radio buttons",
          "object": "reference to the annotation object"
        },
        "choices": "for choices fields, the list of choices presented to the user",
        "defaultvalue": "default value of field",
        "fieldflags": "form field flags from /Ff -- see pdf_form_field_flag_e in qpdf/Constants.h",
        "fieldtype": "field type",
        "fullname": "full name of field",
        "ischeckbox": "whether field is a checkbox",
        "ischoice": "whether field is a list, combo, or dropdown",
        "isradiobutton": "whether field is a radio button -- buttons in a single group share a parent",
        "istext": "whether field is a text field",
        "mappingname": "mapping name of field",
        "object": "reference to this form field",
        "pageposfrom1": "position of containing page numbered from 1",
        "parent": "reference to this field's parent",
        "partialname": "partial name of field",
        "quadding": "field quadding -- number indicating left, center, or right",
        "value": "value of field"
      }
    ],
    "hasacroform": "whether the document has interactive forms",
    "needappearances": "whether the form fields' appearance streams need to be regenerated"
  },
  "attachments": {
    "<attachment-key>": {
      "description": "description of attachment",
      "filespec": "object containing the file spec",
      "names": {
        "<name-key>": "file name for key"
      },
      "preferredcontents": "most preferred embedded file stream",
      "preferredname": "most preferred file name",
      "streams": {
        "<stream-key>": {
          "checksum": "MD5 checksum or null",
          "creationdate": "ISO-8601 creation date or null",
          "mimetype": "mime type or null",
          "modificationdate": "ISO-8601 modification date or null"
        }
      }
    }
  },
  "encrypt": {
    "capabilities": {
      "accessibility": "allow extraction for accessibility?",
      "extract": "allow extraction?",
      "modify": "allow all modifications?",
      "modifyannotations": "allow modifying annotations?",
      "modifyassembly": "allow modifying document assembly?",
      "modifyforms": "allow modifying forms?",
      "modifyother": "allow other modifications?",
      "printhigh": "allow high resolution printing?",
      "printlow": "allow low resolution printing?"
    },
    "encrypted": "whether the document is encrypted",
    "ownerpasswordmatched": "whether supplied password matched owner password; always false for non-encrypted files",
    "parameters": {
      "P": "P value from Encrypt dictionary",
      "R": "R value from Encrypt dictionary",
      "V": "V value from Encrypt dictionary",
      "bits": "encryption key bit length",
      "filemethod": "encryption method for attachments",
      "key": "encryption key; will be null unless --show-encryption-key was specified",
      "method": "overall encryption method: none, mixed, RC4, AESv2, AESv3",
      "streammethod": "encryption method for streams",
      "stringmethod": "encryption method for string"
    },
    "recovereduserpassword": "If the owner password was used to recover the user password, reveal user password; otherwise null",
    "userpasswordmatched": "whether supplied password matched user password; always false for non-encrypted files"
  },
  "outlines": [
    {
      "dest": "outline destination dictionary",
      "destpageposfrom1": "position of destination page in document numbered from 1; null if not known",
      "kids": "array of descendent outlines",
      "object": "reference to this outline",
      "open": "whether the outline is displayed expanded",
      "title": "outline title"
    }
  ],
  "pagelabels": [
    {
      "index": "starting page position starting from zero",
      "label": "page label dictionary"
    }
  ],
  "pages": [
    {
      "contents": [
        "reference to each content stream"
      ],
      "images": [
        {
          "bitspercomponent": "bits per component",
          "colorspace": "color space",
          "decodeparms": [
            "decode parameters for image data"
          ],
          "filter": [
            "filters applied to image data"
          ],
          "filterable": "whether image data can be decoded using the decode level qpdf was invoked with",
          "height": "image height",
          "name": "name of image in XObject table",
          "object": "reference to image stream",
          "width": "image width"
        }
      ],
      "label": "page label dictionary, or null if none",
      "object": "reference to original page object",
      "outlines": [
        {
          "dest": "outline destination dictionary",
          "object": "reference to outline that targets this page",
          "title": "outline title"
        }
      ],
      "pageposfrom1": "position of page in document numbering from 1"
    }
  ],
  "parameters": {
    "decodelevel": "decode level used to determine stream filterability"
  },
  "qpdf": [
    {
      "calledgetallpages": "whether getAllPages was called",
      "jsonversion": "numeric JSON version",
      "maxobjectid": "highest object ID in output, ignored on input",
      "pdfversion": "PDF version as x.y",
      "pushedinheritedpageresources": "whether inherited attributes were pushed to the page level"
    },
    {
      "<obj:n n R|trailer>": "json representation of object"
    }
  ],
  "version": "JSON format serial number; increased for non-compatible changes"
}


```

因此为测试套编写错误