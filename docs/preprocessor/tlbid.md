---
title: tlbid
ms.date: 10/18/2018
f1_keywords:
- tlbid
helpviewer_keywords:
- tlbid attribute
ms.assetid: 54b06785-191b-4e77-a9a5-485f2b4acb09
ms.openlocfilehash: 31b71f7c195a7e2ee649b40197551e4ff5efda2c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50584513"
---
# <a name="tlbid"></a>tlbid

**C++ 固有の仕様**

プライマリ タイプ ライブラリ以外のライブラリの読み込みを許可します。

## <a name="syntax"></a>構文

```
tlbid(number)
```

### <a name="parameters"></a>パラメーター

*数*<br/>
`filename` のタイプ ライブラリの番号。

## <a name="remarks"></a>Remarks

複数のタイプ ライブラリを使用してプライマリ タイプ ライブラリ以外のライブラリを読み込むことが可能に 1 つの DLL に組み込まれているかどうかは**tlbid**します。

例えば:

```cpp
#import <MyResource.dll> tlbid(2)
```

上の式は、下の式と同等です。

```cpp
LoadTypeLib("MyResource.dll\\2");
```

**END C 固有の仕様**

## <a name="see-also"></a>関連項目

[#import の属性](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)