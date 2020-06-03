---
title: AsyncStatusInternal 列挙型
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::Details::AsyncStatusInternal
helpviewer_keywords:
- AsyncStatusInternal enumeration
ms.assetid: b783923f-3f1c-4487-9384-be572cbc62d7
ms.openlocfilehash: 0eadd1e3a287feecd36b00b231b42c31218352c1
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214150"
---
# <a name="asyncstatusinternal-enumeration"></a>AsyncStatusInternal 列挙型

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
enum AsyncStatusInternal;
```

## <a name="remarks"></a>解説

非同期操作の状態と `Windows::Foundation::AsyncStatus` 列挙体の内部列挙間のマッピングを指定します。

## <a name="members"></a>メンバー

`_Created`<br/>
`::Windows::Foundation::AsyncStatus::Created` と同じ意味です。

`_Started`<br/>
`::Windows::Foundation::AsyncStatus::Started` と同じ意味です。

`_Completed`<br/>
`::Windows::Foundation::AsyncStatus::Completed` と同じ意味です。

`_Cancelled`<br/>
`::Windows::Foundation::AsyncStatus::Cancelled` と同じ意味です。

`_Error`<br/>
`::Windows::Foundation::AsyncStatus::Error` と同じ意味です。

## <a name="requirements"></a>必要条件

**ヘッダー:** async .h

**名前空間:** Microsoft:: WRL::D etails

## <a name="see-also"></a>参照

[Microsoft::WRL::Details 名前空間](microsoft-wrl-details-namespace.md)
