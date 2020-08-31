---
title: エンディアン列挙型
description: スカラー型のエンディアンを指定するために使用される列挙型
ms.date: 08/27/2020
f1_keywords:
- bit/std::endian
helpviewer_keywords:
- std::endian
ms.openlocfilehash: 78df181e20d0e5d72508bd0fc86118528a312d6b
ms.sourcegitcommit: 3628707bc17c99aac7aac27eb126cc2eaa4d07b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "89194760"
---
# <a name="endian-enum"></a>エンディアン列挙型

すべてのスカラー型のエンディアンを示します。

## <a name="syntax"></a>構文

```cpp
enum class endian {
    little = 0,
    big = 1,
    native = little
 };
```

### <a name="members"></a>メンバー

|要素|説明|
|-|-|
| `little` | スカラー型がリトルエンディアンであることを示します。 つまり、最下位バイトが最小のアドレスに格納されます。 たとえば、 `0x1234` は格納され `0x34` `0x12` ます。  |
| `big` | スカラー型がビッグエンディアンであることを示します。つまり、最上位バイトが最小のアドレスに格納されます。 たとえば、 `0x1234` は格納され `0x12` `0x34` ます。  |

## <a name="remarks"></a>注釈

すべてのネイティブスカラー型は、ターゲットを Microsoft Visual C++ するプラットフォーム (x86、x64、ARM、ARM64) のリトルエンディアンです。

## <a name="requirements"></a>必要条件

**ヘッダー:**\<bit>

**名前空間:** std

`/std:c++latest` 必須

## <a name="see-also"></a>関連項目

[\<bit>](../standard-library/bit.md)  
