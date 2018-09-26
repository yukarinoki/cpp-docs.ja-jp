---
title: _WAIT_CHILD、_WAIT_GRANDCHILD | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- _WAIT_GRANDCHILD
- WAIT_CHILD
- WAIT_GRANDCHILD
- _WAIT_CHILD
dev_langs:
- C++
helpviewer_keywords:
- WAIT_CHILD constant
- WAIT_GRANDCHILD constant
- _WAIT_CHILD constant
- _WAIT_GRANDCHILD constant
ms.assetid: 7acd96fa-d118-4339-bb00-e5afaf286945
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7dd7b3fab51c382413c507831572afedd824c3f7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46018341"
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