---
title: パス フィールドの制限 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- _MAX_EXT
- _MAX_DIR
- _MAX_PATH
- _MAX_FNAME
- _MAX_DRIVE
dev_langs:
- C++
helpviewer_keywords:
- path field constants
- MAX_FNAME constant
- _MAX_DIR constant
- _MAX_DRIVE constant
- paths, maximum limit
- _MAX_PATH constant
- MAX_DRIVE constant
- _MAX_FNAME constant
- _MAX_EXT constant
- MAX_DIR constant
- MAX_EXT constant
ms.assetid: 2b5d0e43-1347-45b4-8397-24a8a45c444e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0672245a87cdbcf2a4a6dba6d36c675f3faafbc5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32390395"
---
# <a name="path-field-limits"></a>パス フィールドの制限

## <a name="syntax"></a>構文

```cpp
#include <stdlib.h>
```

## <a name="remarks"></a>コメント

これらの定数は、パスやパス内の個々のフィールドなどの最大長を定義します。

|定数|説明|
|--------------|-------------|
|`_MAX_DIR`|ディレクトリのコンポーネントの最大長|
|`_MAX_DRIVE`|ドライブのコンポーネントの最大長|
|`_MAX_EXT`|拡張機能コンポーネントの最大長|
|`_MAX_FNAME`|ファイル名のコンポーネントの最大長|
|`_MAX_PATH`|完全なパスの最大長|

> [!NOTE]
> C ランタイムでは最大 32768 文字のパスの長さがサポートされますが、このように長いパスがサポートされるかどうかは、オペレーティング システム、特にファイル システム次第です。 FAT32 ファイル システムとの完全な下位互換性を維持するために、フィールドの合計は `_MAX_PATH` を超えないようにする必要があります。 Windows の NTFS ファイル システムでは、最大 32768 文字の長さのパスがサポートされますが、Unicode API を使用する場合に限ります。 長いパス名を使用する場合は、パスに \\\\?\ の文字のプレフィックスを付けて、C ランタイム関数の Unicode バージョンを使用します。

## <a name="see-also"></a>関連項目

[グローバル定数](../c-runtime-library/global-constants.md)