---
description: '詳細情報: _com_ptr_t:: CreateInstance'
title: _com_ptr_t::CreateInstance
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::CreateInstance
helpviewer_keywords:
- CreateInstance method [C++]
ms.assetid: ab89b0e1-9da3-4784-a079-58b17340f111
ms.openlocfilehash: dd7ef236f25c22b25c9c083aea8439f5f5175d5b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295524"
---
# <a name="_com_ptr_tcreateinstance"></a>_com_ptr_t::CreateInstance

**Microsoft 固有の仕様**

またはを指定して、オブジェクトの新しいインスタンスを作成し `CLSID` `ProgID` ます。

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
`CLSID`オブジェクトの。

*clsidString*<br/>
`CLSID`("**{**" で始まる) またはを保持する Unicode 文字列 `ProgID` 。

*clsidStringA*<br/>
`CLSID`("**{**" で始まる) またはを保持する、ANSI コードページを使用するマルチバイト文字列 `ProgID` 。

*dwClsContext*<br/>
実行可能コードを実行するコンテキスト。

*pOuter*<br/>
[集計](../atl/aggregation.md)の不明な外部。

## <a name="remarks"></a>解説

これらのメンバー関数は、`CoCreateInstance` を呼び出して新しい COM オブジェクトを作成し、このスマート ポインターのインターフェイス型を照会します。 結果のポインターは、この `_com_ptr_t` オブジェクトの中にカプセル化されます。 `Release` は、以前にカプセル化されたポインターの参照カウントをデクリメントするために呼び出されます。 このルーチンは、成功または失敗を示す HRESULT を返します。

- **CreateInstance (**  *rclsid* **、**  *dwclscontext*  **)** を指定して、オブジェクトの新しい実行中のインスタンスを作成し `CLSID` ます。

- **CreateInstance (***clsidstring* **、***dwclscontext***)**`CLSID`("**{**" で始まる) またはを保持する Unicode 文字列を指定して、オブジェクトの新しい実行中のインスタンスを作成し `ProgID` ます。      

- **CreateInstance (***clsidstringa* **、***dwclscontext***)**`CLSID`("**{**" で始まる) またはを保持するマルチバイト文字列を指定して、オブジェクトの実行中の新しいインスタンスを作成し `ProgID` ます。       [MultiByteToWideChar](/windows/win32/api/stringapiset/nf-stringapiset-multibytetowidechar)を呼び出します。これは、文字列が OEM コードページではなく ANSI コードページに含まれていることを前提としています。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_com_ptr_t クラス](../cpp/com-ptr-t-class.md)
