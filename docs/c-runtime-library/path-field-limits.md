---
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
ms.openlocfilehash: 8db9961bd2d5b5b3ea9d3addad3c26737b4f5199
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80171399"
---
# <a name="path-field-limits"></a>パス フィールドの制限

## <a name="syntax"></a>構文

```cpp
#include <stdlib.h>
```

## <a name="remarks"></a>解説

これらの定数は、パスやパス内の個々のフィールドなどの最大長を定義します。

|常時|意味|
|--------------|-------------|
|`_MAX_DIR`|ディレクトリのコンポーネントの最大長|
|`_MAX_DRIVE`|ドライブのコンポーネントの最大長|
|`_MAX_EXT`|拡張機能コンポーネントの最大長|
|`_MAX_FNAME`|ファイル名のコンポーネントの最大長|
|`_MAX_PATH`|完全なパスの最大長|

> [!NOTE]
> C ランタイムでは最大 32768 文字のパスの長さがサポートされますが、このように長いパスがサポートされるかどうかは、オペレーティング システム、特にファイル システム次第です。 FAT32 ファイル システムとの完全な下位互換性を維持するために、フィールドの合計は `_MAX_PATH` を超えないようにする必要があります。 Windows の NTFS ファイル システムでは、最大 32768 文字の長さのパスがサポートされますが、Unicode API を使用する場合に限ります。 長いパス名を使用する場合は、パスに \\\\?\ の文字のプレフィックスを付けて、C ランタイム関数の Unicode バージョンを使用します。

## <a name="see-also"></a>参照

[グローバル定数](../c-runtime-library/global-constants.md)
