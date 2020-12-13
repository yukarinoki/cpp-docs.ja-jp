---
description: '詳細情報: tlbid import 属性'
title: tlbid import 属性
ms.date: 08/29/2019
f1_keywords:
- tlbid
helpviewer_keywords:
- tlbid attribute
ms.assetid: 54b06785-191b-4e77-a9a5-485f2b4acb09
ms.openlocfilehash: 9bbf15f64c1813013fcd839a2d4f0a34c9872aff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339052"
---
# <a name="tlbid-import-attribute"></a>tlbid import 属性

**C++ 固有の仕様**

プライマリ タイプ ライブラリ以外のライブラリの読み込みを許可します。

## <a name="syntax"></a>構文

> **#import** *タイプライブラリ* **tlbid (** *number* **)**

### <a name="parameters"></a>パラメーター

*少数*\
*タイプライブラリ dll* 内のタイプライブラリの番号。

## <a name="remarks"></a>解説

複数のタイプライブラリが1つの DLL に組み込まれている場合、 **tlbid** を使用してプライマリタイプライブラリ以外のライブラリを読み込むことができます。

次に例を示します。

```cpp
#import <MyResource.dll> tlbid(2)
```

は以下に匹敵します。

```cpp
LoadTypeLib("MyResource.dll\\2");
```

**END C++ 固有の仕様**

## <a name="see-also"></a>関連項目

[#import 属性](../preprocessor/hash-import-attributes-cpp.md)\
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)
