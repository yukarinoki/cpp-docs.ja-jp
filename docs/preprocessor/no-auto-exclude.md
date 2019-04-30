---
title: no_auto_exclude
ms.date: 11/04/2016
f1_keywords:
- no_auto_exclude
helpviewer_keywords:
- no_auto_exclude attribute
ms.assetid: 3241ef9c-758a-4e86-bdc5-37da6072430f
ms.openlocfilehash: 06bde7535bd181057750ab9dd4c3999321b4990c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62371699"
---
# <a name="noautoexclude"></a>no_auto_exclude
**C++ 固有の仕様**

自動除外を無効にします。

## <a name="syntax"></a>構文

```
no_auto_exclude
```

## <a name="remarks"></a>Remarks

タイプ ライブラリは、システム ヘッダーまたはその他のタイプ ライブラリで定義された項目の定義を含むことがあります。 `#import` は、そのような項目を自動的に除外して多重定義エラーを回避します。 これが完了したら、[コンパイラの警告 (レベル 3) C4192](../error-messages/compiler-warnings/compiler-warning-level-3-c4192.md)を除外するには、各項目が発行されます。 この自動除外を、この属性を使用して無効にすることができます。

**END C 固有の仕様**

## <a name="see-also"></a>関連項目

[#import の属性](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)