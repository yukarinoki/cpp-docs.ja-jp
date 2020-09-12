---
title: endian 列挙型
description: スカラー型のエンディアンを指定するために使用される列挙型
ms.date: 08/27/2020
f1_keywords:
- bit/std::endian
helpviewer_keywords:
- std::endian
ms.openlocfilehash: b535bc009fbdc0b047444a6bc2ca36eed7a6d1cb
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "90040081"
---
# <a name="endian-enum"></a>endian 列挙型

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

## <a name="requirements"></a>要件

**ヘッダー:**\<bit>

**名前空間:** std

[/std: c + + latest](../build/reference/std-specify-language-standard-version.md) が必要です。

## <a name="see-also"></a>関連項目

[\<bit>](../standard-library/bit.md)  
