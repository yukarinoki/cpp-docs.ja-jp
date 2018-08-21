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
ms.openlocfilehash: 08d5df7893aa5390a6e577e3c26424864f7c3a8f
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39465767"
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
 既定では、 [_com_raise_error](../cpp/com-raise-error.md)すべての COM エラーを処理します。 使用してこの動作を変更する **_set_com_error_handler**を独自のエラー処理関数を呼び出します。  
  
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
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<comdef.h >  
  
 **Lib:** 場合、 **wchar_t をネイティブ型**コンパイラ オプションは、comsuppw.lib または comsuppwd.lib を使用します。 場合**wchar_t をネイティブ型**オフ、comsupp.lib を使用します。 「[/Zc:wchar_t (wchar_t をネイティブ型として認識)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ COM のグローバル関数](../cpp/compiler-com-global-functions.md)