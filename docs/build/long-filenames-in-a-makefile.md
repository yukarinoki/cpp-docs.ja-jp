---
title: メイクファイルの長いファイル名 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, long filenames
- long filenames
ms.assetid: 626d56fc-8879-46ba-9c2d-dd386c78cccc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9d69abd9fa67db7c1ec2e5dede0ebd5629d21e7b
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45714546"
---
# <a name="long-filenames-in-a-makefile"></a>メイクファイルでの長いファイル名

次のように、二重引用符で長いファイル名を囲みます。

```
all : "VeryLongFileName.exe"
```

## <a name="see-also"></a>関連項目

[メイクファイルの内容](../build/contents-of-a-makefile.md)