---
title: ptr::operator = |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- ptr.operator=
- msclr.com.ptr.operator=
- msclr::com::ptr::operator=
- ptr::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator=
ms.assetid: 58619910-46c0-4db8-b183-c811b23b2df1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a8a8b87afba71836876554e1abbe04014cb09772
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46075083"
---
# <a name="ptroperator"></a>ptr::operator=
COM オブジェクトのアタッチ、`com::ptr`します。  
  
## <a name="syntax"></a>構文  
  
```  
ptr<_interface_type> % operator=(  
   _interface_type * _right  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
*(_r)*<br/>
アタッチする COM インターフェイス ポインター。  
  
## <a name="return-value"></a>戻り値  
 追跡参照、`com::ptr`します。  
  
## <a name="exceptions"></a>例外  
 場合、 `com::ptr` 、COM オブジェクトへの参照を既に所有している`operator=`スロー<xref:System.InvalidOperationException>します。  
  
## <a name="remarks"></a>Remarks  
 COM オブジェクトを割り当て、 `com::ptr` COM オブジェクトを参照しますが、呼び出し元の参照を解放しません。  
  
 この演算子と同じ効果を持つ`Attach`します。  
  
## <a name="example"></a>例  
 この例の実装を使用する CLR クラス、`com::ptr`のプライベート メンバーをラップする`IXMLDOMDocument`オブジェクト。  `ReplaceDocument`メンバー関数の最初の呼び出し`Release`いずれかで所有していたオブジェクトおよび、使用`operator=`新しい document オブジェクトをアタッチします。  
  
```  
// comptr_op_assign.cpp  
// compile with: /clr /link msxml2.lib  
#include <msxml2.h>  
#include <msclr\com\ptr.h>  
  
#import <msxml3.dll> raw_interfaces_only  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
using namespace msclr;  
  
// a ref class that uses a com::ptr to contain an   
// IXMLDOMDocument object  
ref class XmlDocument {  
public:  
   // construct the internal com::ptr with a null interface  
   // and use CreateInstance to fill it  
   XmlDocument(String^ progid) {  
      m_ptrDoc.CreateInstance(progid);     
   }  
  
   // replace currently held COM object with another one  
   void ReplaceDocument(IXMLDOMDocument* pDoc) {  
      // release current document object  
      m_ptrDoc.Release();  
      // attach the new document object  
      m_ptrDoc = pDoc;  
   }  
  
   // note that the destructor will call the com::ptr destructor  
   // and automatically release the reference to the COM object  
  
private:  
   com::ptr<IXMLDOMDocument> m_ptrDoc;  
};  
  
// unmanaged function that creates a raw XML DOM Document object  
IXMLDOMDocument* CreateDocument() {  
   IXMLDOMDocument* pDoc = NULL;  
   Marshal::ThrowExceptionForHR(CoCreateInstance(CLSID_DOMDocument30, NULL,  
      CLSCTX_INPROC_SERVER, IID_IXMLDOMDocument, (void**)&pDoc));  
   return pDoc;  
}  
  
// use the ref class to handle an XML DOM Document object  
int main() {  
   IXMLDOMDocument* pDoc = NULL;  
  
   try {  
      // create the class from a progid string  
      XmlDocument doc("Msxml2.DOMDocument.3.0");  
  
      // get another document object from unmanaged function and  
      // store it in place of the one held by the ref class  
      pDoc = CreateDocument();  
      doc.ReplaceDocument(pDoc);  
      // no further need for raw object reference  
      pDoc->Release();  
      pDoc = NULL;  
   }  
   catch (Exception^ e) {  
      Console::WriteLine(e);     
   }  
   finally {  
      if (NULL != pDoc) {  
         pDoc->Release();  
      }  
   }  
}  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー ファイル** \<msclr\com\ptr.h >  
  
 **Namespace** msclr::com  
  
## <a name="see-also"></a>関連項目  
 [ptr のメンバー](../dotnet/ptr-members.md)   
 [ptr::Attach](../dotnet/ptr-attach.md)   
 [ptr::Detach](../dotnet/ptr-detach.md)   
 [ptr::Release](../dotnet/ptr-release.md)