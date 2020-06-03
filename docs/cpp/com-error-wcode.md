---
title: _com_error::WCode
ms.date: 11/04/2016
f1_keywords:
- _com_error::WCode
helpviewer_keywords:
- WCode method [C++]
ms.assetid: f3b21852-f8ea-4e43-bff1-11c2d35454c4
ms.openlocfilehash: 92dffbdbe034ef55be04c1b7d204be6880d8d4b2
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190197"
---
# <a name="_com_errorwcode"></a>_com_error::WCode

**Microsoft 固有の仕様**

カプセル化された HRESULT にマップされた16ビットエラーコードを取得します。

## <a name="syntax"></a>構文

```
WORD WCode ( ) const throw( );
```

## <a name="return-value"></a>戻り値

HRESULT が 0x80040200 ~ 0x8004FFFF の範囲内にある場合、`WCode` メソッドは HRESULT から0x80040200 を引いた値を返します。それ以外の場合は0を返します。

## <a name="remarks"></a>解説

`WCode` メソッドは、COM サポートコードで発生するマッピングを元に戻すために使用されます。 `dispinterface` のプロパティまたはメソッドのラッパーは、引数をパッケージ化して `IDispatch::Invoke`を呼び出すサポートルーチンを呼び出します。 返されたときに、`DISP_E_EXCEPTION` のエラー HRESULT が返された場合、`IDispatch::Invoke`に渡される `EXCEPINFO` 構造からエラー情報が取得されます。 エラーコードは、`EXCEPINFO` 構造の `wCode` メンバーに格納されている16ビット値にするか、`EXCEPINFO` 構造体の `scode` メンバーの完全な32ビット値にすることができます。 16ビット `wCode` が返された場合は、最初に32ビットエラー HRESULT にマップする必要があります。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[_com_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)<br/>
[_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)<br/>
[_com_error クラス](../cpp/com-error-class.md)
