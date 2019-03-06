---
title: LIBRARY
ms.date: 11/04/2016
f1_keywords:
- LIBRARY
helpviewer_keywords:
- LIBRARY .def file statement
ms.assetid: 1d7ccc92-e088-4ef7-9ef0-25c3862cc051
ms.openlocfilehash: 73609be698719da05fff357ba80200c49f598add
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57422668"
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
