---
title: _com_error::wcode |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::WCode
dev_langs:
- C++
helpviewer_keywords:
- WCode method [C++]
ms.assetid: f3b21852-f8ea-4e43-bff1-11c2d35454c4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 810a5c16df1027aba976bea3c165b19f765d15a6
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2018
ms.locfileid: "37941841"
---
# <a name="comerrorwcode"></a>_com_error::WCode
**Microsoft 固有の仕様**  
  
 カプセル化された HRESULT にマップされた 16 ビット エラー コードを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
  
WORD WCode ( ) const throw( );  
  
```  
  
## <a name="return-value"></a>戻り値  
 HRESULT が範囲 0x80040200 を 0x8004FFFF 内にある場合、`WCode`から 0x80040200 を引いた HRESULT を返します。 それ以外の場合、0 を返します。  
  
## <a name="remarks"></a>Remarks  
 `WCode`メソッドを使用して、COM サポート コード内で発生したマッピングを元に戻します。 ラッパーは、`dispinterface`プロパティまたはメソッド呼び出しの引数と呼び出しにパッケージ化するサポート ルーチン`IDispatch::Invoke`します。 戻り時に HRESULT の DISP_E_EXCEPTION が返されたエラーの場合、エラーから情報を取得、`EXCEPINFO`に構造体が渡される`IDispatch::Invoke`します。 エラー コードはいずれかに格納されている 16 ビット値、`wCode`のメンバー、`EXCEPINFO`構造体またはで完全な 32 ビット値、`scode`のメンバー、`EXCEPINFO`構造体。 場合、16 ビット`wCode`返されるか、32 ビットのエラー HRESULT を最初にマップする必要があります。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_com_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)   
 [_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)   
 [_com_error クラス](../cpp/com-error-class.md)