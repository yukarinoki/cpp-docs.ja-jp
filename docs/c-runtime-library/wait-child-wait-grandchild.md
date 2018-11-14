---
title: _WAIT_CHILD、_WAIT_GRANDCHILD
ms.date: 11/04/2016
f1_keywords:
- _WAIT_GRANDCHILD
- WAIT_CHILD
- WAIT_GRANDCHILD
- _WAIT_CHILD
helpviewer_keywords:
- WAIT_CHILD constant
- WAIT_GRANDCHILD constant
- _WAIT_CHILD constant
- _WAIT_GRANDCHILD constant
ms.assetid: 7acd96fa-d118-4339-bb00-e5afaf286945
ms.openlocfilehash: 714b4e79f1c229817a12908aad0d726f74023036
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2018
ms.locfileid: "51524392"
---
# <a name="waitchild-waitgrandchild"></a>_WAIT_CHILD、_WAIT_GRANDCHILD

## <a name="syntax"></a>構文

```

#include <process.h>
```

## <a name="remarks"></a>コメント

`_cwait` 関数は、あらゆるプロセスで他のすべてのプロセスを待機するために使用できます (プロセス ID がわかっている場合)。 アクションの引数は、次の値のいずれかになります。

|定数|説明|
|--------------|-------------|
|`_WAIT_CHILD`|呼び出しプロセスは、指定した新しいプロセスが終了するまで待機します。|
|`_WAIT_GRANDCHILD`|呼び出しプロセスは、指定した新しいプロセスとその新しいプロセスによって生成されたすべてのプロセスが終了するまで待機します。|

## <a name="see-also"></a>参照

[_cwait](../c-runtime-library/reference/cwait.md)<br/>
[グローバル定数](../c-runtime-library/global-constants.md)