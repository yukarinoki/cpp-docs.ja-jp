---
title: _com_ptr_t::GetActiveObject
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::GetActiveObject
helpviewer_keywords:
- GetActiveObject method [C++]
ms.assetid: 2fa94853-0410-4620-91f2-136dae923f9f
ms.openlocfilehash: 84e43de9c40baa3c596c68ed7739471c059cbac7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62154852"
---
# <a name="comptrtgetactiveobject"></a>_com_ptr_t::GetActiveObject

**Microsoft 固有の仕様**

指定したオブジェクトの既存のインスタンスにアタッチ、`CLSID`または`ProgID`します。

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
`CLSID`のオブジェクト。

*clsidString*<br/>
保持する Unicode 文字列、 `CLSID` (以降では"**{**") または`ProgID`します。

*clsidStringA*<br/>
いずれかを保持する ANSI コード ページを使用し、マルチバイト文字列を`CLSID`(以降では"**{**") または`ProgID`します。

## <a name="remarks"></a>Remarks

これらのメンバー関数を呼び出す**GetActiveObject** OLE に登録されている実行中のオブジェクトへのポインターを取得し、このスマート ポインターのクエリはインターフェイス型とします。 結果のポインターは、この `_com_ptr_t` オブジェクトの中にカプセル化されます。 `Release` 以前にカプセル化されたポインターの参照カウントをデクリメントすると呼びます。 このルーチンは、成功または失敗を示す HRESULT を返します。

- **GetActiveObject (**`rclsid`**)** 指定したオブジェクトの既存のインスタンスにアタッチ、`CLSID`します。

- **GetActiveObject (**`clsidString`**)** 保持する Unicode 文字列を指定したオブジェクトの既存のインスタンスにアタッチ、 `CLSID` (以降では"**{**") または、 `ProgID`.

- **GetActiveObject (**`clsidStringA`**)** 保持するマルチバイト文字の文字列を指定したオブジェクトの既存のインスタンスにアタッチ、 `CLSID` (以降では"**{**") または`ProgID`. 呼び出し[MultiByteToWideChar](/windows/desktop/api/stringapiset/nf-stringapiset-multibytetowidechar)、OEM コード ページではなく、ANSI コード ページで、文字列が想定しています。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_com_ptr_t クラス](../cpp/com-ptr-t-class.md)