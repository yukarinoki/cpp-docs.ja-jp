---
title: stdext 名前空間 | Microsoft Docs
ms.custom: ''
ms.date: 09/06/2017
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- stdext
dev_langs:
- C++
helpviewer_keywords:
- _DEFINE_DEPRECATED_HASH_CLASSES symbol
- stdext namespace
ms.assetid: 3e94fc89-0584-424f-bc09-081b73379545
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 302d5b696a3413e36dd76cb931556a3fae7e7615
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="stdext-namespace"></a>stdext 名前空間

メンバー、 [ \<hash_map >](../standard-library/hash-map.md)と[ \<hash_set >](../standard-library/hash-set.md)現在は ISO C 標準の一部がヘッダー ファイルではないです。 そのため、これらの型およびメンバーは、C++ の標準に準拠するように、名前空間 `std` から名前空間 `stdext`に移動されました。

コンパイルするときに[/Ze](../build/reference/za-ze-disable-language-extensions.md)、コンパイラの警告の使用について、既定値は`std`のメンバーに対して、 \<hash_map > および\<hash_set > ヘッダー ファイルです。 この警告を無効にするには、 [warning](../preprocessor/warning.md) プラグマを使用します。

コンパイラでの使用に対してエラーを生成する`std`のメンバーの\<hash_map > および\<hash_set > ヘッダー ファイルが **/Ze**、追加する前に次のディレクティブ`#include`C++ 標準ライブラリ ヘッダー ファイルです。

```cpp
#define _DEFINE_DEPRECATED_HASH_CLASSES 0
```

コンパイルするときに **/Za**、コンパイラ エラーが発生します。

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリの概要](../standard-library/cpp-standard-library-overview.md)

