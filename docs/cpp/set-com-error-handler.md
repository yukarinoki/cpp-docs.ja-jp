---
title: _set_com_error_handler |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- _set_com_error_handler function
ms.assetid: 49fe4fca-5e37-4d83-abaf-15be5ce37f94
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1f516114dbaa9e507491cf669c3371b6b8fbaf11
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2018
ms.locfileid: "37943582"
---
# <a name="setcomerrorhandler"></a>_set_com_error_handler
**Microsoft 固有の仕様**  
  
 COM のエラー処理に使用する既定の関数を置き換えます。  
  
## <a name="syntax"></a>構文  
  
```  
void __stdcall _set_com_error_handler(  
   void (__stdcall *pHandler)(  
      HRESULT hr,   
      IErrorInfo* perrinfo  
   )  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *pHandler*  
 置換する関数へのポインター。  
  
 *hr*  
 HRESULT 情報。  
  
 *perrinfo*  
 `IErrorInfo` オブジェクト。  
  
## <a name="remarks"></a>Remarks  
 既定では、 [_com_raise_error](../cpp/com-raise-error.md)すべての COM エラーを処理します。 この動作は、`_set_com_error_handler` で独自のエラー処理関数を呼び出すことで変更できます。  
  
 置換関数には `_com_raise_error` のシグネチャと等価のシグニチャが必要です。  
  
## <a name="example"></a>例  
  
```cpp 
// _set_com_error_handler.cpp  
// compile with /EHsc  
#include <stdio.h>  
#include <comdef.h>  
#include <comutil.h>  
  
// Importing ado dll to attempt to establish an ado connection.  
// Not related to _set_com_error_handler   
#import "C:\Program Files\Common Files\System\ado\msado15.dll" no_namespace rename("EOF", "adoEOF")  
  
void __stdcall _My_com_raise_error(HRESULT hr, IErrorInfo* perrinfo)  
{  
   throw "Unable to establish the connection!";  
}  
  
int main()  
{  
   _set_com_error_handler(_My_com_raise_error);  
   _bstr_t bstrEmpty(L"");  
   _ConnectionPtr Connection = NULL;  
   try  
   {  
      Connection.CreateInstance(__uuidof(Connection));  
      Connection->Open(bstrEmpty, bstrEmpty, bstrEmpty, 0);   
   }  
   catch(char* errorMessage)  
   {  
      printf("Exception raised: %s\n", errorMessage);  
   }  
  
   return 0;  
}  
```  
  
```Output  
Exception raised: Unable to establish the connection!  
```  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<comdef.h >  
  
 **Lib:** 場合、 **wchar_t をネイティブ型**コンパイラ オプションは、comsuppw.lib または comsuppwd.lib を使用します。 場合**wchar_t をネイティブ型**オフ、comsupp.lib を使用します。 「[/Zc:wchar_t (wchar_t をネイティブ型として認識)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ COM のグローバル関数](../cpp/compiler-com-global-functions.md)