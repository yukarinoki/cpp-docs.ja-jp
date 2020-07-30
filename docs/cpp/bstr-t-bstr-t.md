---
title: _bstr_t::_bstr_t
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::_bstr_t
helpviewer_keywords:
- BSTR object
- _bstr_t method [C++]
- _bstr_t class
ms.assetid: 116d994e-5a72-4351-afbe-866c80b4c165
ms.openlocfilehash: 843d6aa0e04595143d7da585e95d58e97fe80db0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221836"
---
# <a name="_bstr_t_bstr_t"></a>_bstr_t::_bstr_t

**Microsoft 固有の仕様**

`_bstr_t` オブジェクトを構築します。

## <a name="syntax"></a>構文

```
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

#### <a name="parameters"></a>パラメーター

*s1*<br/>
コピーされる `_bstr_t` オブジェクト。

*s2*<br/>
マルチバイト文字列。

*s3*<br/>
Unicode 文字列。

*var*<br/>
[_Variant_t](../cpp/variant-t-class.md)オブジェクト。

*bstr*<br/>
既存の `BSTR` オブジェクトです。

*fCopy*<br/>
**`false`** の場合、を呼び出すことによってコピーを作成せずに、 *bstr*引数が新しいオブジェクトにアタッチされ `SysAllocString` ます。

## <a name="remarks"></a>解説

`_bstr_t` のコンストラクターについて次の表で説明します。

|コンストラクター|説明|
|-----------------|-----------------|
|`_bstr_t( )`|`_bstr_t`Null オブジェクトをカプセル化する既定のオブジェクトを構築 `BSTR` します。|
|`_bstr_t( _bstr_t&`  `s1`  `)`|別のコピーとして `_bstr_t` オブジェクトを構築します。<br /><br /> これは、 *shallow* `BSTR` 新しいものを作成するのではなく、カプセル化されたオブジェクトの参照カウントをインクリメントする簡易コピーです。|
|`_bstr_t( char*`  `s2`  `)`|`_bstr_t` を呼び出して新しい `SysAllocString` オブジェクトを作成することで `BSTR` オブジェクトを構築し、そのオブジェクトをカプセル化します。<br /><br /> このコンストラクターは、マルチバイトから Unicode への変換を最初に実行します。|
|`_bstr_t( wchar_t*`  `s3`  `)`|`_bstr_t` を呼び出して新しい `SysAllocString` オブジェクトを作成することで `BSTR` オブジェクトを構築し、そのオブジェクトをカプセル化します。|
|`_bstr_t( _variant_t&`  `var`  `)`|最初に、カプセル化された VARIANT オブジェクトから `_bstr_t` オブジェクトを取得することによって、`_variant_t` オブジェクトから `BSTR` オブジェクトを構築します。|
|`_bstr_t( BSTR`  `bstr` `, bool`  `fCopy`  `)`|(`_bstr_t` 文字列ではなく) 既存の `BSTR` から `wchar_t*` オブジェクトを構築します。 *Fcopy*が false の場合、指定されたは `BSTR` を使用して新しいコピーを作成せずに、新しいオブジェクトにアタッチされ `SysAllocString` ます。<br /><br /> このコンストラクターは、インターフェイス メソッドによって返される `BSTR` をカプセル化し、その所有権を得るために、タイプ ライブラリ ヘッダーのラッパー関数によって使用されます。|

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_bstr_t クラス](../cpp/bstr-t-class.md)<br/>
[_variant_t クラス](../cpp/variant-t-class.md)
