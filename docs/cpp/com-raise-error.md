---
title: _com_raise_error |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_raise_error
dev_langs:
- C++
helpviewer_keywords:
- _com_raise_error function
ms.assetid: a98226c2-c3fe-44f1-8ff5-85863de11cd6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f38a0d97b90f1512e5f16b3bd147bda3e0614e4f
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2018
ms.locfileid: "37943511"
---
# <a name="comraiseerror"></a>_com_raise_error
**Microsoft 固有の仕様**  
  
 スローされます、 [_com_error](../cpp/com-error-class.md)エラーに応答します。  
  
## <a name="syntax"></a>構文  
  
```  
  
void __stdcall _com_raise_error(  
   HRESULT hr,  
   IErrorInfo* perrinfo = 0  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *hr*  
 HRESULT 情報。  
  
 *perrinfo*  
 `IErrorInfo` オブジェクト。  
  
## <a name="remarks"></a>Remarks  
 `_com_raise_error`、定義されている\<comdef.h >、同じ名前とプロトタイプのユーザー作成のバージョンで置き換えることができます。 `#import` を使用し、C++ 例外処理を使用しない場合は、こうすることができます。 その場合、ユーザー バージョンので`_com_raise_error`実行することがあります、`longjmp`またはメッセージ ボックスを表示し、停止します。 ユーザー バージョンで返すことはできません。コンパイラ COM サポート コードがそれを予期していないためです。  
  
 使用することも[_set_com_error_handler](../cpp/set-com-error-handler.md)を既定のエラー処理関数を置き換えます。  
  
 既定では、`_com_raise_error` は次のように定義されています。  
  
```cpp  
void __stdcall _com_raise_error(HRESULT hr, IErrorInfo* perrinfo) {  
   throw _com_error(hr, perrinfo);  
}  
```  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<comdef.h >  
  
 **Lib:** 場合、 **wchar_t をネイティブ型**コンパイラ オプションは、comsuppw.lib または comsuppwd.lib を使用します。 場合**wchar_t をネイティブ型**オフ、comsupp.lib を使用します。 「[/Zc:wchar_t (wchar_t をネイティブ型として認識)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ COM グローバル関数](../cpp/compiler-com-global-functions.md)   
 [_set_com_error_handler](../cpp/set-com-error-handler.md)