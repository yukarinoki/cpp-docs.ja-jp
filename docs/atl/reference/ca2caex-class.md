---
title: CA2CAEX クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CA2CAEX
- ATLCONV/ATL::CA2CAEX
- ATLCONV/ATL::CA2CAEX::CA2CAEX
- ATLCONV/ATL::CA2CAEX::m_psz
dev_langs:
- C++
helpviewer_keywords:
- CA2CAEX class
ms.assetid: 388e7c1d-a144-474c-a182-b15f69a74bd8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4abf96e3850f88b58e138745536ffc40aef11b68
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46024542"
---
# <a name="ca2caex-class"></a>CA2CAEX クラス

このクラスは、文字列変換マクロ CA2CTEX と CT2CAEX、typedef CA2CA によって使用されます。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<int t_nBufferLength = 128>
class CA2CAEX
```

#### <a name="parameters"></a>パラメーター

*t_nBufferLength*<br/>
変換プロセスで使用されるバッファーのサイズ。 既定の長さは 128 バイトです。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CA2CAEX::CA2CAEX](#ca2caex)|コンストラクターです。|
|[CA2CAEX:: ~ CA2CAEX](#dtor)|デストラクターです。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CA2CAEX::operator LPCSTR](#operator_lpcstr)|変換演算子。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CA2CAEX::m_psz](#m_psz)|ソース文字列が格納されるデータ メンバー。|

## <a name="remarks"></a>Remarks

追加の機能が必要でない限り、独自のコードで CA2CTEX、CT2CAEX、または CA2CA を使用します。

このクラスは、安全にループ内で使用し、スタック オーバーフローが発生しません。 既定では、ATL 変換クラスとマクロは、現在のスレッドの ANSI コード ページを変換に使用します。

次のマクロは、このクラスに基づいています。

- CA2CTEX

- CT2CAEX

次の typedef は、このクラスに基づいています。

- CA2CA

これらのテキスト変換マクロの詳細については、次を参照してください。 [ATL と MFC 文字列変換マクロ](string-conversion-macros.md)します。

## <a name="example"></a>例

参照してください[ATL と MFC 文字列変換マクロ](string-conversion-macros.md)のこれらの文字列変換マクロの使用例についてはします。

## <a name="requirements"></a>要件

**ヘッダー:** atlconv.h

##  <a name="ca2caex"></a>  CA2CAEX::CA2CAEX

コンストラクターです。

```
CA2CAEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2CAEX(LPCSTR psz) throw(...);
```

### <a name="parameters"></a>パラメーター

*2 つ*<br/>
変換するテキスト文字列。

*nCodePage*<br/>
このクラスで使用されていません。

### <a name="remarks"></a>Remarks

翻訳のために必要なバッファーを作成します。

##  <a name="dtor"></a>  CA2CAEX:: ~ CA2CAEX

デストラクターです。

```
~CA2CAEX() throw();
```

### <a name="remarks"></a>Remarks

割り当てられたバッファーを解放します。

##  <a name="m_psz"></a>  CA2CAEX::m_psz

ソース文字列が格納されるデータ メンバー。

```
LPCSTR m_psz;
```

##  <a name="operator_lpcstr"></a>  CA2CAEX::operator LPCSTR

変換演算子。

```
operator LPCSTR() const throw();
```

### <a name="return-value"></a>戻り値

LPCSTR の種類としては、テキスト文字列を返します。

## <a name="see-also"></a>関連項目

[CA2AEX クラス](../../atl/reference/ca2aex-class.md)<br/>
[CA2WEX クラス](../../atl/reference/ca2wex-class.md)<br/>
[CW2AEX クラス](../../atl/reference/cw2aex-class.md)<br/>
[CW2CWEX クラス](../../atl/reference/cw2cwex-class.md)<br/>
[CW2WEX クラス](../../atl/reference/cw2wex-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
