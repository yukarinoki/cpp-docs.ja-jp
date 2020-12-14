---
description: '詳細については、次を参照してください: _com_ptr_t:: GetActiveObject'
title: _com_ptr_t::GetActiveObject
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::GetActiveObject
helpviewer_keywords:
- GetActiveObject method [C++]
ms.assetid: 2fa94853-0410-4620-91f2-136dae923f9f
ms.openlocfilehash: 96784e73d91d7be4b0674e09278183fc62e60af2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295472"
---
# <a name="_com_ptr_tgetactiveobject"></a>_com_ptr_t::GetActiveObject

**Microsoft 固有の仕様**

またはを指定して、オブジェクトの既存のインスタンスにアタッチ `CLSID` `ProgID` します。

## <a name="syntax"></a>構文

```
HRESULT GetActiveObject(
   const CLSID& rclsid
) throw( );
HRESULT GetActiveObject(
   LPCWSTR clsidString
) throw( );
HRESULT GetActiveObject(
   LPCSTR clsidStringA
) throw( );
```

#### <a name="parameters"></a>パラメーター

*rclsid*<br/>
`CLSID`オブジェクトの。

*clsidString*<br/>
`CLSID`("**{**" で始まる) またはを保持する Unicode 文字列 `ProgID` 。

*clsidStringA*<br/>
`CLSID`("**{**" で始まる) またはを保持する、ANSI コードページを使用するマルチバイト文字列 `ProgID` 。

## <a name="remarks"></a>解説

これらのメンバー関数は、 **Getactiveobject** を呼び出して、OLE に登録されている実行中のオブジェクトへのポインターを取得し、このスマートポインターのインターフェイス型を照会します。 結果のポインターは、この `_com_ptr_t` オブジェクトの中にカプセル化されます。 `Release` は、以前にカプセル化されたポインターの参照カウントをデクリメントするために呼び出されます。 このルーチンは、成功または失敗を示す HRESULT を返します。

- **Getactiveobject (** `rclsid` **)** は、を指定したオブジェクトの既存のインスタンスにアタッチ `CLSID` します。    

- **Getactiveobject (** `clsidString` **)** `CLSID` は、("**{**" で始まる) またはのいずれかを保持する Unicode 文字列を指定して、オブジェクトの既存のインスタンスにアタッチし `ProgID` ます。    

- **Getactiveobject (** `clsidStringA` **)** `CLSID` は、("**{**" で始まる) またはのいずれかを保持するマルチバイト文字列を指定して、オブジェクトの既存のインスタンスにアタッチし `ProgID` ます。     [MultiByteToWideChar](/windows/win32/api/stringapiset/nf-stringapiset-multibytetowidechar)を呼び出します。これは、文字列が OEM コードページではなく ANSI コードページに含まれていることを前提としています。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_com_ptr_t クラス](../cpp/com-ptr-t-class.md)
