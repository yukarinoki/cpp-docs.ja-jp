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
ms.openlocfilehash: a1b7c713b5d82ff54250b622f2d4afe17abac468
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87185607"
---
# <a name="_variant_t-extractors"></a>_variant_t 抽出

**Microsoft 固有の仕様**

カプセル化されたオブジェクトからデータを抽出 `VARIANT` します。

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

カプセル化されたから生データを抽出 `VARIANT` します。 が適切な型では `VARIANT` ない場合、 `VariantChangeType` は変換を試行するために使用され、エラーが発生するとエラーが生成されます。

- **operator short ()****`short`** 整数値を抽出します。

- **operator long ()****`long`** 整数値を抽出します。

- **operator float ()** 数値を抽出 **`float`** します。

- **double 演算子 ()****`double`** 整数値を抽出します。

- **OPERATOR CY ()** オブジェクトを抽出 `CY` します。

- **bool () 演算子**値を抽出 **`bool`** します。

- **演算子 DECIMAL ()** 値を抽出 `DECIMAL` します。

- **BYTE () 演算子**値を抽出 `BYTE` します。

- **operator _bstr_t ()** オブジェクトにカプセル化された文字列を抽出し `_bstr_t` ます。

- **Operator IDispatch \* ()** は、カプセル化されたからディスパッチインターフェイスポインターを抽出 `VARIANT` します。 `AddRef`は結果のポインターに対して呼び出されるため、を呼び出すと `Release` 解放されます。

- **Operator IUnknown \* ()** は、カプセル化されたから COM インターフェイスポインターを抽出 `VARIANT` します。 `AddRef`は結果のポインターに対して呼び出されるため、を呼び出すと `Release` 解放されます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_variant_t クラス](../cpp/variant-t-class.md)
