---
description: 詳細については、「パスフィールドの制限」を参照してください。
title: パス フィールドの制限
ms.date: 11/04/2016
f1_keywords:
- _MAX_EXT
- _MAX_DIR
- _MAX_PATH
- _MAX_FNAME
- _MAX_DRIVE
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
ms.openlocfilehash: 41698d946e45a78f9b89f40fdd3c7c58af5d4354
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97213482"
---
# <a name="path-field-limits"></a>パス フィールドの制限

## <a name="syntax"></a>構文

```cpp
#include <stdlib.h>
```

## <a name="remarks"></a>解説

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
