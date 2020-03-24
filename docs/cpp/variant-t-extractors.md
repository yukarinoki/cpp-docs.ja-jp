---
title: _variant_t 抽出
ms.date: 11/04/2016
f1_keywords:
- _variant_t.operatordouble
- operatorlong
- _variant_t::operator_bstr_t
- operatordouble
- _variant_t.operatorCY
- operatorCY
- _variant_t::operatorCY
- _variant_t::operatordouble
- operatorfloat
- operatorBYTE
- _variant_t.operatorDECIMAL
- _variant_t::operatorlong
- operatorIDispatch
- _variant_t.operatorBYTE
- operatorDECIMAL
- _variant_t.operator_bstr_t
- _variant_t::operatorDECIMAL
- _variant_t.operatorIUnknown
- _variant_t.operatorlong
- _variant_t::operatorIDispatch
- _variant_t::operatorIUnknown
- operatorIUnknown
- _variant_t.operatorbool
- _variant_t::operatorBYTE
- _variant_t.operatorfloat
- operator_bstr_t
- _variant_t::operatorbool
- operatorshort
- _variant_t::operatorshort
- _variant_t::operatorfloat
- _variant_t.operatorIDispatch
- _variant_t.operatorshort
helpviewer_keywords:
- extractors, _variant_t class
- operator CY
- operator IDispatch
- operator SHORT
- operator double
- operator long
- operator _bstr_t
- operator DECIMAL
- operator float
- operator bool
- operator BYTE
- operator IUnknown
ms.assetid: 33c1782f-045a-4673-9619-1d750efc83a9
ms.openlocfilehash: 685df7285e58e0cf2ceeded5ac27641364897298
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187701"
---
# <a name="_variant_t-extractors"></a>_variant_t 抽出

**Microsoft 固有の仕様**

カプセル化された `VARIANT` オブジェクトからデータを抽出します。

## <a name="syntax"></a>構文

```
operator short( ) const;
operator long( ) const;
operator float( ) const;
operator double( ) const;
operator CY( ) const;
operator _bstr_t( ) const;
operator IDispatch*( ) const;
operator bool( ) const;
operator IUnknown*( ) const;
operator DECIMAL( ) const;
operator BYTE( ) const;
operator VARIANT() const throw();
operator char() const;
operator unsigned short() const;
operator unsigned long() const;
operator int() const;
operator unsigned int() const;
operator __int64() const;
operator unsigned __int64() const;
```

## <a name="remarks"></a>解説

カプセル化された `VARIANT`から生データを抽出します。 `VARIANT` が適切な型でない場合は、`VariantChangeType` を使用して変換が試行され、エラーが発生したときにエラーが生成されます。

- **operator short ()** **短**整数値を抽出します。

- **operator long ()** **長**整数値を抽出します。

- **operator float ()** **Float**数値を抽出します。

- **double 演算子 ()** **2**つの整数値を抽出します。

- **OPERATOR CY ()** `CY` オブジェクトを抽出します。

- **bool () 演算子** **ブール**値を抽出します。

- **演算子 DECIMAL ()** `DECIMAL` 値を抽出します。

- **BYTE () 演算子**`BYTE` 値を抽出します。

- **operator _bstr_t ()** `_bstr_t` オブジェクトにカプセル化された文字列を抽出します。

- **演算子 IDispatch\*()** カプセル化された `VARIANT`からディスパッチインターフェイスポインターを抽出します。 結果のポインターに対して `AddRef` が呼び出されるため、`Release` を呼び出して解放します。

- **操作 IUnknown\*()** カプセル化された `VARIANT`から COM インターフェイスポインターを抽出します。 結果のポインターに対して `AddRef` が呼び出されるため、`Release` を呼び出して解放します。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[_variant_t クラス](../cpp/variant-t-class.md)
