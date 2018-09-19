---
title: ライブラリ |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- LIBRARY
dev_langs:
- C++
helpviewer_keywords:
- LIBRARY .def file statement
ms.assetid: 1d7ccc92-e088-4ef7-9ef0-25c3862cc051
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 43b14e8e8ff4871ba4319c7f4fac5545e72e710b
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45723555"
---
# <a name="library"></a>LIBRARY

DLL を作成するリンクを示します。 同時に、リンクは、ビルドで .exp ファイルを使用しない場合、インポート ライブラリを作成します。

```
LIBRARY [library][BASE=address]
```

## <a name="remarks"></a>Remarks

*ライブラリ*引数が DLL の名前を指定します。 使用することも、 [/out](../../build/reference/out-output-file-name.md) DLL の出力名を指定するリンカー オプション。

ベース =*アドレス*引数は、オペレーティング システムが DLL の読み込みに使用するベース アドレスを設定します。 この引数は、0x10000000 の既定の DLL の場所を上書きします。 説明を参照して、 [/base](../../build/reference/base-base-address.md)オプションの詳細については、ベース アドレス。

使用してください、 [/DLL](../../build/reference/dll-build-a-dll.md) DLL をビルドするときに、リンカー オプション。

## <a name="see-also"></a>関連項目

[モジュール定義ステートメントに関する規則](../../build/reference/rules-for-module-definition-statements.md)