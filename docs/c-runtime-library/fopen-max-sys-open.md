---
title: FOPEN_MAX、_SYS_OPEN | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- _SYS_OPEN
- FOPEN_MAX
dev_langs:
- C++
helpviewer_keywords:
- SYS_OPEN constant
- _SYS_OPEN constant
- FOPEN_MAX constant
- files [C++], maximum open
- maximum number of files
- open files, maximum
ms.assetid: 39cf5196-250a-459d-ae90-ce3d99f79039
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 18653eaae84e619e549146bd721dee3199f90ac5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46090894"
---
# <a name="fopenmax-sysopen"></a>FOPEN_MAX、_SYS_OPEN

## <a name="syntax"></a>構文

```

#include <stdio.h>

```

## <a name="remarks"></a>コメント

これは、同時に開くことのできるファイルの最大数です。 `FOPEN_MAX` は、ANSI との互換性がある名前です。 `_SYS_OPEN` は、既存のコードとの互換性のために提供されています。

## <a name="see-also"></a>参照

[グローバル定数](../c-runtime-library/global-constants.md)