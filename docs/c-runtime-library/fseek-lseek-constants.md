---
title: fseek 定数と _lseek 定数 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- SEEK_END
- SEEK_SET
- SEEK_CUR
dev_langs:
- C++
helpviewer_keywords:
- SEEK_SET constant
- SEEK_END constant
- SEEK_CUR constant
ms.assetid: 9deeb13e-5aa3-4c33-80d8-721c80a4de9d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3d48ead4532638461962a3bf88d2321cee775ab3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46087659"
---
# <a name="fseek-lseek-constants"></a>fseek 定数と _lseek 定数

## <a name="syntax"></a>構文

```

#include <stdio.h>

```

## <a name="remarks"></a>コメント

*origin* 引数は初期位置を指定し、次のマニフェスト定数のいずれかになります。

|定数|説明|
|--------------|-------------|
|`SEEK_END`|ファイルの終端|
|`SEEK_CUR`|ファイル ポインターの現在の位置|
|`SEEK_SET`|ファイルの先頭|

## <a name="see-also"></a>参照

[fseek、_fseeki64](../c-runtime-library/reference/fseek-fseeki64.md)<br/>
[_lseek、_lseeki64](../c-runtime-library/reference/lseek-lseeki64.md)<br/>
[グローバル定数](../c-runtime-library/global-constants.md)