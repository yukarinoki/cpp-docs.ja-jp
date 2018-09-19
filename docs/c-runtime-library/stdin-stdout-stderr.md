---
title: stdin、stdout、stderr |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- stdin
- stderr
- stdout
dev_langs:
- C++
helpviewer_keywords:
- stdout function
- standard output stream
- standard error stream
- stdin function
- standard input stream
- stderr function
ms.assetid: badd4735-596d-4498-857c-ec8b7e670e4c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a36d5fd60a19222e6f802e5a14037fb01ff865f5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46071979"
---
# <a name="stdin-stdout-stderr"></a>stdin、stdout、stderr

## <a name="syntax"></a>構文

```

      FILE *stdin; 
FILE *stdout; 
FILE *stderr; 
#include <stdio.h>
```

## <a name="remarks"></a>コメント

これらは、入力、出力、エラー出力の標準ストリームです。

既定では、標準入力はキーボードから読み取られ、標準出力と標準エラーは画面に出力されます。

標準ストリームにアクセスするには、次のストリーム ポインターを使用できます。

|ポインター|ストリーム|
|-------------|------------|
|`stdin`|標準入力|
|**stdout**|標準出力|
|`stderr`|標準エラー|

これらのポインターは、関数への引数として使用できます。 **getchar** や `putchar` などのいくつかの関数では、`stdin` と **stdout** が自動的に使用されます。

これらのポインターは定数であり、新しい値を割り当てることはできません。 ディスク ファイルやその他のデバイスにストリームをリダイレクトするには、`freopen` 関数を使用できます。 オペレーティング システムでは、プログラムの標準入力と出力をコマンド レベルでリダイレクトすることができます。

## <a name="see-also"></a>参照

[ストリーム入出力](../c-runtime-library/stream-i-o.md)<br/>
[グローバル定数](../c-runtime-library/global-constants.md)