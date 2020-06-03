---
title: _com_ptr_t::GetActiveObject
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::GetActiveObject
helpviewer_keywords:
- GetActiveObject method [C++]
ms.assetid: 2fa94853-0410-4620-91f2-136dae923f9f
ms.openlocfilehash: ea8059a039b77811dd54d4a4937ad746b7ca0937
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80170802"
---
# <a name="_com_ptr_tgetactiveobject"></a>_com_ptr_t::GetActiveObject

**Microsoft 固有の仕様**

`CLSID` または `ProgID`を指定して、オブジェクトの既存のインスタンスにアタッチします。

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
オブジェクトの `CLSID`。

*clsidString*<br/>
`CLSID` (" **{** " で始まる) または `ProgID`のいずれかを保持する Unicode 文字列。

*clsidStringA*<br/>
ANSI コードページを使用するマルチバイト文字列。 `CLSID` (" **{** " で始まる) または `ProgID`を保持します。

## <a name="remarks"></a>解説

これらのメンバー関数は、 **Getactiveobject**を呼び出して、OLE に登録されている実行中のオブジェクトへのポインターを取得し、このスマートポインターのインターフェイス型を照会します。 結果のポインターは、この `_com_ptr_t` オブジェクトの中にカプセル化されます。 `Release` は、以前にカプセル化されたポインターの参照カウントをデクリメントするために呼び出されます。 このルーチンは、成功または失敗を示す HRESULT を返します。

- **Getactiveobject (** `rclsid` **)** `CLSID`を指定して、オブジェクトの既存のインスタンスにアタッチします。

- **Getactiveobject (** `clsidString` **)** `CLSID` (" **{** " で始まる) または `ProgID`を保持する Unicode 文字列を指定して、オブジェクトの既存のインスタンスにアタッチします。

- **Getactiveobject (** `clsidStringA` **)** `CLSID` (" **{** " で始まる) または `ProgID`を保持するマルチバイト文字列を指定して、オブジェクトの既存のインスタンスにアタッチします。 [MultiByteToWideChar](/windows/win32/api/stringapiset/nf-stringapiset-multibytetowidechar)を呼び出します。これは、文字列が OEM コードページではなく ANSI コードページに含まれていることを前提としています。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[_com_ptr_t クラス](../cpp/com-ptr-t-class.md)
