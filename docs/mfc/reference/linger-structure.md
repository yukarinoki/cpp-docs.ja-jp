---
title: LINGER 構造体
ms.date: 11/04/2016
f1_keywords:
- LINGER
helpviewer_keywords:
- LINGER structure [MFC]
ms.assetid: 1fb1c5bf-a64e-4a6c-89d6-1734e4fdbb1b
ms.openlocfilehash: 78f1a5ce993373ea9e477262f0779515c52dbd8c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50495318"
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

## <a name="requirements"></a>必要条件

**ヘッダー:** winsock2.h

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CAsyncSocket::GetSockOpt](../../mfc/reference/casyncsocket-class.md#getsockopt)<br/>
[CAsyncSocket::SetSockOpt](../../mfc/reference/casyncsocket-class.md#setsockopt)

