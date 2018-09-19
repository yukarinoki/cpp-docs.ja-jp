---
title: _com_ptr_t::CreateInstance |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::CreateInstance
dev_langs:
- C++
helpviewer_keywords:
- CreateInstance method [C++]
ms.assetid: ab89b0e1-9da3-4784-a079-58b17340f111
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: aa81e25b30061881dc00a401dc386647a8cdb73b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46094235"
---
# <a name="comptrtcreateinstance"></a>_com_ptr_t::CreateInstance

**Microsoft 固有の仕様**

指定したオブジェクトの新しいインスタンスを作成、`CLSID`または`ProgID`します。

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
`CLSID`のオブジェクト。

*clsidString*<br/>
保持する Unicode 文字列、 `CLSID` (以降では"**{**") または`ProgID`します。

*clsidStringA*<br/>
いずれかを保持する ANSI コード ページを使用し、マルチバイト文字列を`CLSID`(以降では"**{**") または`ProgID`します。

*dwClsContext*<br/>
実行可能コードを実行するコンテキスト。

*pOuter*<br/>
不明な外部の[集計](../atl/aggregation.md)します。

## <a name="remarks"></a>Remarks

これらのメンバー関数は、`CoCreateInstance` を呼び出して新しい COM オブジェクトを作成し、このスマート ポインターのインターフェイス型を照会します。 結果のポインターは、この `_com_ptr_t` オブジェクトの中にカプセル化されます。 `Release` 以前にカプセル化されたポインターの参照カウントをデクリメントすると呼びます。 このルーチンは、成功または失敗を示す HRESULT を返します。

- **CreateInstance (***rclsid* **、***dwClsContext***)** を指定したオブジェクトの実行中の新しいインスタンスを作成します`CLSID`。

- **CreateInstance (***clsidString* **、***dwClsContext***)** 指定したオブジェクトの実行中の新しいインスタンスを作成します。保持する Unicode 文字列、 `CLSID` (以降では"**{**") または`ProgID`します。

- **CreateInstance (***clsidStringA* **、***dwClsContext***)** 指定したオブジェクトの実行中の新しいインスタンスを作成します。いずれかを保持するマルチバイト文字の文字列を`CLSID`(以降では"**{**") または`ProgID`します。 呼び出し[MultiByteToWideChar](/windows/desktop/api/stringapiset/nf-stringapiset-multibytetowidechar)、OEM コード ページではなく、ANSI コード ページで、文字列が想定しています。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_com_ptr_t クラス](../cpp/com-ptr-t-class.md)