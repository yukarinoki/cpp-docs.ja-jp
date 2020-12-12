---
description: '詳細情報: stdext 名前空間'
title: stdext 名前空間
ms.date: 09/06/2017
f1_keywords:
- stdext
helpviewer_keywords:
- _DEFINE_DEPRECATED_HASH_CLASSES symbol
- stdext namespace
ms.assetid: 3e94fc89-0584-424f-bc09-081b73379545
ms.openlocfilehash: bb81dde22014ec91f7212ce4313c21a8410f30a9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97153786"
---
# <a name="stdext-namespace"></a>stdext 名前空間

[\<hash_map>](../standard-library/hash-map.md) [\<hash_set>](../standard-library/hash-set.md) ヘッダーファイルとヘッダーファイルのメンバーは、現在 ISO C++ 標準の一部ではありません。 そのため、これらの型およびメンバーは、C++ の標準に準拠するように、名前空間 `std` から名前空間 `stdext`に移動されました。

既定である [/ze](../build/reference/za-ze-disable-language-extensions.md)を使用してコンパイルすると、コンパイラは、 `std` \<hash_map> ヘッダーファイルとヘッダーファイルのメンバーに対してを使用することを警告し \<hash_set> ます。 この警告を無効にするには、 [warning](../preprocessor/warning.md) プラグマを使用します。

とのヘッダーファイルのメンバーに対して、を使用するためのエラーがコンパイラによって生成されるようにするには `std` \<hash_map> \<hash_set> 、 `#include` C++ 標準ライブラリのヘッダーファイルの前に次のディレクティブを追加します。

```cpp
#define _DEFINE_DEPRECATED_HASH_CLASSES 0
```

**/Za** を使用してコンパイルすると、コンパイラによってエラーが生成されます。

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリの概要](../standard-library/cpp-standard-library-overview.md)
