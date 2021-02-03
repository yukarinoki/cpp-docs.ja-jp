---
description: '詳細については、「_bstr_t:: _bstr_t」を参照してください。'
title: _bstr_t::_bstr_t
ms.date: 02/02/2021
f1_keywords:
- _bstr_t::_bstr_t
helpviewer_keywords:
- BSTR object
- _bstr_t method [C++]
- _bstr_t class
ms.openlocfilehash: 0e6913a45b1c4d542e495bc59bc5871f533a1573
ms.sourcegitcommit: c20734f18d3d49bb38b1628c68b53b54b3eeeb03
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "99522912"
---
# `_bstr_t::_bstr_t`

**Microsoft 固有の仕様**

`_bstr_t` オブジェクトを構築します。

## <a name="syntax"></a>構文

```cpp
_bstr_t( ) throw( );
_bstr_t(
   const _bstr_t& s1
) throw( );
_bstr_t(
   const char* s2
);
_bstr_t(
   const wchar_t* s3
);
_bstr_t(
   const _variant_t& var
);
_bstr_t(
   BSTR bstr,
   bool fCopy
);
```

### <a name="parameters"></a>パラメーター

*`s1`*\
コピーされる `_bstr_t` オブジェクト。

*`s2`*\
マルチバイト文字列。

*`s3`*\
Unicode 文字列。

*`var`*\
[_Variant_t](../cpp/variant-t-class.md)オブジェクト。

*`bstr`*\
既存の `BSTR` オブジェクトです。

*`fCopy`*\
の場合、を **`false`** *`bstr`* 呼び出してコピーを作成せずに、引数が新しいオブジェクトにアタッチされ `SysAllocString` ます。

## <a name="remarks"></a>解説

クラスには、いくつかのコンストラクターが用意されてい `_bstr_t` ます。

`_bstr_t( )`\
`_bstr_t`Null オブジェクトをカプセル化する既定のオブジェクトを構築 `BSTR` します。

`_bstr_t( _bstr_t& s1 )`\
別のコピーとして `_bstr_t` オブジェクトを構築します。 このコンストラクターは、新しいものを作成するのではなく、カプセル化されたオブジェクトの参照カウントをインクリメントする *簡易* コピーを `BSTR` 作成します。

`_bstr_t( char* s2 )`\
`_bstr_t` を呼び出して新しい `SysAllocString` オブジェクトを作成することで `BSTR` オブジェクトを構築し、そのオブジェクトをカプセル化します。 このコンストラクターは、マルチバイトから Unicode への変換を最初に実行します。

`_bstr_t( wchar_t* s3 )`\
`_bstr_t` を呼び出して新しい `SysAllocString` オブジェクトを作成することで `BSTR` オブジェクトを構築し、そのオブジェクトをカプセル化します。

`_bstr_t( _variant_t& var )`\
`_bstr_t`最初に、カプセル化されたオブジェクトからオブジェクトを取得して、オブジェクトからオブジェクトを構築 `_variant_t` `BSTR` `VARIANT` します。

`_bstr_t( BSTR bstr, bool fCopy )`\
(`_bstr_t` 文字列ではなく) 既存の `BSTR` から `wchar_t*` オブジェクトを構築します。 がの場合 *`fCopy`* **`false`** 、指定されたは、 `BSTR` を使用して新しいコピーを作成せずに、新しいオブジェクトにアタッチされ `SysAllocString` ます。 このコンストラクターは、 `BSTR` インターフェイスメソッドによって返されるをカプセル化し、その所有権を取得するために、タイプライブラリヘッダーのラッパー関数によって使用されます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[`_bstr_t` 講義](../cpp/bstr-t-class.md)\
[`_variant_t` 講義](../cpp/variant-t-class.md)
