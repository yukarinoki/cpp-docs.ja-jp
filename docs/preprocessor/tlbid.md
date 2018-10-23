---
title: tlbid |Microsoft Docs
ms.custom: ''
ms.date: 10/18/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- tlbid
dev_langs:
- C++
helpviewer_keywords:
- tlbid attribute
ms.assetid: 54b06785-191b-4e77-a9a5-485f2b4acb09
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6324ec9a64a0d1c47dab8d1beee021f6c8752a96
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2018
ms.locfileid: "49807979"
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