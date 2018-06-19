---
title: _com_error::wcode |Microsoft ドキュメント
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
ms.openlocfilehash: 1354d490446795e55b41fa0c548e8dd8aa38c71b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32411537"
---
# <a name="comerrorwcode"></a>_com_error::WCode
**Microsoft 固有の仕様**  
  
 カプセル化された `HRESULT` にマップされた 16 ビット エラー コードを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
  
WORD WCode ( ) const throw( );  
  
```  
  
## <a name="return-value"></a>戻り値  
 場合、`HRESULT`が範囲 0x80040200 を 0x8004FFFF 内に、 **WCode**メソッドを返します、`HRESULT`から; 0x80040200 を引いたそれ以外の場合、ゼロを返します。  
  
## <a name="remarks"></a>コメント  
 **WCode** COM サポート コードで発生したマッピングを元に戻すメソッドを使用します。 ラッパー、 **dispinterface**プロパティまたはメソッドの呼び出しで引数をパッケージするサポート ルーチンを呼び出すと**idispatch::invoke**です。 関数が戻るとき場合エラー`HRESULT`の`DISP_E_EXCEPTION`からエラー情報を取得、返される、 **EXCEPINFO**に構造体が渡される**idispatch::invoke**です。 エラー コードは、いずれかに格納された 16 ビット値、`wCode`のメンバー、 **EXCEPINFO**構造体またはで完全な 32 ビット値、 **scode**のメンバー、 **EXCEPINFO**構造体。 16 ビットの `wCode` が返された場合は、最初に 32 ビットのエラー `HRESULT` にマップする必要があります。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_com_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)   
 [_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)   
 [_com_error クラス](../cpp/com-error-class.md)