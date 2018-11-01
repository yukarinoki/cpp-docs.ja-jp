---
title: SOCKADDR 構造体
ms.date: 11/04/2016
f1_keywords:
- SOCKADDR
helpviewer_keywords:
- SOCKADDR structure [MFC]
ms.assetid: df1ed66a-f4b8-43f8-8db8-8c2533d25f68
ms.openlocfilehash: 68d5261c6520b5baee8495b72a0b9d234a35a185
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50543846"
---
# <a name="sockaddr-structure"></a>SOCKADDR 構造体

`SOCKADDR` 構造体は Windows Socket 通信に参加するコンピューターのインターネット プロトコル (IP) アドレスを格納するために使用されます。

## <a name="syntax"></a>構文

```
struct sockaddr {
    unsigned short sa_family;
    char sa_data[14];
};
```

#### <a name="parameters"></a>パラメーター

*sa_family*<br/>
ソケット アドレス ファミリ。

*sa_data*<br/>
さまざまなソケット アドレス構造体すべてのうち最大のサイズ。

## <a name="remarks"></a>Remarks

Microsoft TCP/IP Sockets Developer's Kit では、インターネット アドレス ドメインのみをサポートします。 アドレスの各部分の値を実際に入力するために、`SOCKADDR_IN` データ構造体を使用します。この構造体は、このアドレス形式専用です。 `SOCKADDR` と `SOCKADDR_IN` の各データ構造体は同じサイズです。 2 つの構造体の種類の間で切り替えを行うには、単純に割り当てを行います。

## <a name="requirements"></a>必要条件

**ヘッダー:** winsock2.h

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[SOCKADDR_IN 構造体](../../mfc/reference/sockaddr-in-structure.md)<br/>
[CAsyncSocket::Create](../../mfc/reference/casyncsocket-class.md#create)<br/>
[CSocket::Create](../../mfc/reference/csocket-class.md#create)

