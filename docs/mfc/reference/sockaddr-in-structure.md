---
title: SOCKADDR_IN 構造体
ms.date: 11/04/2016
f1_keywords:
- SOCKADDR_IN
helpviewer_keywords:
- SOCKADDR_IN structure [MFC]
ms.assetid: e8cd7c34-78bd-4e28-a990-eb3ca070b7a6
ms.openlocfilehash: 22d02b2e3c6fd7151e59cad0f3233539c04a16e0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50431227"
---
# <a name="sockaddrin-structure"></a>SOCKADDR_IN 構造体

インターネット アドレス ファミリでは、ソケットを接続するローカルまたはリモート エンドポイント アドレスを指定するために、Windows ソケットによって `SOCKADDR_IN` の構造体が使用されます。

## <a name="syntax"></a>構文

```
struct sockaddr_in{
    short sin_family;
    unsigned short sin_port;
struct in_addr sin_addr;
    char sin_zero[8];
};
```

#### <a name="parameters"></a>パラメーター

*これは必須*<br/>
アドレス ファミリ (AF_INET をする必要があります)。

*いった*<br/>
IP ポート。

*いった*<br/>
IP アドレス。

*sin_zero*<br/>
`SOCKADDR` と同じサイズに構造体を変更する埋め込み。

## <a name="remarks"></a>Remarks

これはインターネット アドレス ファミリに特有の `SOCKADDR` 構造体の形態であり、`SOCKADDR` にキャストできます。

この構造体の IP アドレスのコンポーネントのタイプは`IN_ADDR`します。 `IN_ADDR` Windows ソケットのヘッダー ファイル WINSOCK の構造を定義します。次のように H:

```
struct in_addr {
    union {
        struct {
            unsigned char s_b1, s_b2, s_b3, s_b4;
        } S_un_b;
        struct {
            unsigned short s_w1, s_w2;
        } S_un_w;
        unsigned long S_addr;
    } S_un;
};
```

## <a name="requirements"></a>必要条件

**ヘッダー:** winsock2.h

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[SOCKADDR 構造体](../../mfc/reference/sockaddr-structure.md)
