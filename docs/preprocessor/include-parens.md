---
title: include()
ms.date: 10/18/2018
f1_keywords:
- include()
helpviewer_keywords:
- include() attribute
ms.assetid: 86c9dcb2-d9e0-4fd5-97d7-0bb3e23d6ecc
ms.openlocfilehash: 1208f14a9f6b3724dd5353df57213baa3910d07f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383738"
---
# <a name="include"></a>include()

**C++ 固有の仕様**

自動除外を無効にします。

## <a name="syntax"></a>構文

```
include("Name1"[,"Name2", ...])
```

### <a name="parameters"></a>パラメーター

*Name1*<br/>
強制的に含まれる最初の項目。

*Name2*<br/>
強制的に含める 2 番目の項目 (必要な場合)。

## <a name="remarks"></a>Remarks

タイプ ライブラリは、システム ヘッダーまたはその他のタイプ ライブラリで定義された項目の定義を含むことがあります。 `#import` は、そのような項目を自動的に除外して多重定義エラーを回避します。 示されているアイテムが除外されている場合[コンパイラの警告 (レベル 3) C4192](../error-messages/compiler-warnings/compiler-warning-level-3-c4192.md)、付与しないようにされて、この属性を使用して自動除外を無効にすることができます。 この属性は、任意の数の引数を受け取ることができます。各引数は、含まれるタイプ ライブラリ項目の名前です。

**END C 固有の仕様**

## <a name="see-also"></a>関連項目

[#import の属性](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)