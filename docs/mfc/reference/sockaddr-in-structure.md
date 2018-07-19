---
title: SOCKADDR_IN 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- SOCKADDR_IN
dev_langs:
- C++
helpviewer_keywords:
- SOCKADDR_IN structure [MFC]
ms.assetid: e8cd7c34-78bd-4e28-a990-eb3ca070b7a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5e5ec6ebf4329ff03c75240dc7cec93e9ba46331
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37885739"
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
 *これは必須*  
 アドレス ファミリ (AF_INET をする必要があります)。  
  
 *いった*  
 IP ポート。  
  
 *いった*  
 IP アドレス。  
  
 *sin_zero*  
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
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [SOCKADDR 構造体](../../mfc/reference/sockaddr-structure.md)
