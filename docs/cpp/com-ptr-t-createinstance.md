---
title: _com_ptr_t::CreateInstance
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::CreateInstance
helpviewer_keywords:
- CreateInstance method [C++]
ms.assetid: ab89b0e1-9da3-4784-a079-58b17340f111
ms.openlocfilehash: 2ec4e90c8f0c1009cc47e9022a09b3b8f7dbb284
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190002"
---
# <a name="_com_ptr_tcreateinstance"></a>_com_ptr_t::CreateInstance

**Microsoft 固有の仕様**

`CLSID` または `ProgID`を指定して、オブジェクトの新しいインスタンスを作成します。

## <a name="syntax"></a>構文

```
HRESULT CreateInstance(
   const CLSID& rclsid,
   IUnknown* pOuter=NULL,
   DWORD dwClsContext = CLSCTX_ALL
) throw( );
HRESULT CreateInstance(
   LPCWSTR clsidString,
   IUnknown* pOuter=NULL,
   DWORD dwClsContext = CLSCTX_ALL
) throw( );
HRESULT CreateInstance(
   LPCSTR clsidStringA,
   IUnknown* pOuter=NULL,
   DWORD dwClsContext = CLSCTX_ALL
) throw( );
```

#### <a name="parameters"></a>パラメーター

*rclsid*<br/>
オブジェクトの `CLSID`。

*clsidString*<br/>
`CLSID` (" **{** " で始まる) または `ProgID`のいずれかを保持する Unicode 文字列。

*clsidStringA*<br/>
ANSI コードページを使用するマルチバイト文字列。 `CLSID` (" **{** " で始まる) または `ProgID`を保持します。

*dwClsContext*<br/>
実行可能コードを実行するコンテキスト。

*pOuter*<br/>
[集計](../atl/aggregation.md)の不明な外部。

## <a name="remarks"></a>解説

これらのメンバー関数は、`CoCreateInstance` を呼び出して新しい COM オブジェクトを作成し、このスマート ポインターのインターフェイス型を照会します。 結果のポインターは、この `_com_ptr_t` オブジェクトの中にカプセル化されます。 `Release` は、以前にカプセル化されたポインターの参照カウントをデクリメントするために呼び出されます。 このルーチンは、成功または失敗を示す HRESULT を返します。

- **CreateInstance (** *rclsid* **、** *dwclscontext* **)** `CLSID`を指定して、オブジェクトの新しい実行中のインスタンスを作成します。

- **CreateInstance (** *clsidstring* **、** *dwclscontext* **)** `CLSID` (" **{** " で始まる) または `ProgID`のいずれかを保持する Unicode 文字列を指定して、オブジェクトの新しい実行インスタンスを作成します。

- **CreateInstance (** *clsidstringa* **、** *dwclscontext* **)** `CLSID` (" **{** " で始まる) または `ProgID`のいずれかを保持するマルチバイト文字列を指定して、オブジェクトの実行中の新しいインスタンスを作成します。 [MultiByteToWideChar](/windows/win32/api/stringapiset/nf-stringapiset-multibytetowidechar)を呼び出します。これは、文字列が OEM コードページではなく ANSI コードページに含まれていることを前提としています。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[_com_ptr_t クラス](../cpp/com-ptr-t-class.md)
