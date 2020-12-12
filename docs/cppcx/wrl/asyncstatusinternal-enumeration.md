---
description: 詳細については、「AsyncStatusInternal 列挙型」を参照してください。
title: AsyncStatusInternal 列挙型
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::Details::AsyncStatusInternal
helpviewer_keywords:
- AsyncStatusInternal enumeration
ms.assetid: b783923f-3f1c-4487-9384-be572cbc62d7
ms.openlocfilehash: 3227699a0e7b8933dc5839e65fb3489328d3b1f5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175795"
---
# <a name="asyncstatusinternal-enumeration"></a>AsyncStatusInternal 列挙型

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
enum AsyncStatusInternal;
```

## <a name="remarks"></a>解説

非同期操作の状態と列挙体の内部列挙間のマッピングを指定し `Windows::Foundation::AsyncStatus` ます。

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

## <a name="requirements"></a>要件

**ヘッダー:** async .h

**名前空間:** Microsoft:: WRL::D etails

## <a name="see-also"></a>関連項目

[Microsoft:: WRL::D etails 名前空間](microsoft-wrl-details-namespace.md)
