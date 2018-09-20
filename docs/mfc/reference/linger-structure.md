---
title: LINGER 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- LINGER
dev_langs:
- C++
helpviewer_keywords:
- LINGER structure [MFC]
ms.assetid: 1fb1c5bf-a64e-4a6c-89d6-1734e4fdbb1b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2dda3aab3c4a967c82a699058868edc8fc183984
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46386380"
---
# <a name="linger-structure"></a>LINGER 構造体

`LINGER`構造がの SO_LINGER と SO_DONTLINGER のオプションを操作するために使用される`CAsyncSocket::GetSockOpt`します。

## <a name="syntax"></a>構文

```
struct linger {
    u_short l_onoff;            // option on/off
    u_short l_linger;           // linger time
};
```

## <a name="remarks"></a>Remarks

メンバー関数でブロックされている SO_DONTLINGER オプションを設定できません`Close`未送信のデータの送信を待機中にします。 SO_LINGER の設定と同じには、このオプションを設定`l_onoff`を 0 に設定します。

## <a name="requirements"></a>要件

**ヘッダー:** winsock2.h

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CAsyncSocket::GetSockOpt](../../mfc/reference/casyncsocket-class.md#getsockopt)<br/>
[CAsyncSocket::SetSockOpt](../../mfc/reference/casyncsocket-class.md#setsockopt)

