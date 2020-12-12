---
description: '詳細情報: ライブラリ'
title: LIBRARY
ms.date: 11/04/2016
f1_keywords:
- LIBRARY
helpviewer_keywords:
- LIBRARY .def file statement
ms.assetid: 1d7ccc92-e088-4ef7-9ef0-25c3862cc051
ms.openlocfilehash: 3d8c63f323568949cf2fb30935d2557755346422
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199533"
---
# <a name="library"></a>LIBRARY

DLL を作成するようにリンクを指示します。 同時に、ビルドで .exp ファイルが使用されていない限り、リンクによってインポートライブラリが作成されます。

```
LIBRARY [library][BASE=address]
```

## <a name="remarks"></a>解説

*Library* 引数は DLL の名前を指定します。 また、 [/out](out-output-file-name.md) リンカーオプションを使用して、DLL の出力名を指定することもできます。

BASE =*address* 引数は、オペレーティングシステムが DLL を読み込むために使用するベースアドレスを設定します。 この引数は、0x10000000 の既定の DLL の場所よりも優先されます。 ベースアドレスの詳細については、 [/base](base-base-address.md) オプションの説明を参照してください。

DLL をビルドするときは、 [/dll](dll-build-a-dll.md) リンカーオプションを必ず使用してください。

## <a name="see-also"></a>関連項目

[Module-Definition ステートメントの規則](rules-for-module-definition-statements.md)
