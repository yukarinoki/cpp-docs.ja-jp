---
description: '詳細情報: _com_error:: WCode'
title: _com_error::WCode
ms.date: 11/04/2016
f1_keywords:
- _com_error::WCode
helpviewer_keywords:
- WCode method [C++]
ms.assetid: f3b21852-f8ea-4e43-bff1-11c2d35454c4
ms.openlocfilehash: e3a19e5ae6c98cb38445e5eaa822474b2a852135
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295732"
---
# <a name="_com_errorwcode"></a>_com_error::WCode

**Microsoft 固有の仕様**

カプセル化された HRESULT にマップされた16ビットエラーコードを取得します。

## <a name="syntax"></a>構文

```
WORD WCode ( ) const throw( );
```

## <a name="return-value"></a>戻り値

HRESULT が 0x80040200 ~ 0x8004FFFF の範囲内にある場合、 `WCode` メソッドは hresult から0x80040200 を引いた値を返します。それ以外の場合は0を返します。

## <a name="remarks"></a>解説

`WCode`メソッドは、COM サポートコード内で発生するマッピングを元に戻すために使用されます。 `dispinterface`プロパティまたはメソッドのラッパーは、引数と呼び出しをパッケージ化するサポートルーチンを呼び出し `IDispatch::Invoke` ます。 が返された場合、のエラー HRESULT `DISP_E_EXCEPTION` が返されると、に渡された構造からエラー情報が取得され `EXCEPINFO` `IDispatch::Invoke` ます。 エラーコードには、構造体のメンバーに格納されている16ビット値、 `wCode` `EXCEPINFO` または `scode` 構造体のメンバーの完全な32ビット値のいずれかを指定でき `EXCEPINFO` ます。 16ビットが返された場合は `wCode` 、最初に32ビットエラー HRESULT にマップする必要があります。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_com_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)<br/>
[_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)<br/>
[_com_error クラス](../cpp/com-error-class.md)
