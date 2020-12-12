---
description: 詳細については、「リンカーツールの警告 LNK4286」を参照してください。
title: リンカー ツールの警告 LNK4286
ms.date: 04/15/2019
f1_keywords:
- LNK4286
helpviewer_keywords:
- LNK4286
ms.openlocfilehash: 6a1e397967857ae3f982bf8f5e55f4bf74c9abe4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97244447"
---
# <a name="linker-tools-warning-lnk4286"></a>リンカー ツールの警告 LNK4286

> '*filename_1. .obj*' で定義されたシンボル '*symbol*' は '*filename_2 .obj*' によってインポートされます

シンボルが同じイメージ内のオブジェクトファイル *filename_1* で定義されている場合でも、*シンボル* に [__declspec (dllimport)](../../cpp/dllexport-dllimport.md)が指定されました。 `__declspec(dllimport)`この警告を解決するには、修飾子を削除します。

## <a name="remarks"></a>解説

Warning LNK4286 は、より一般的なバージョンの [リンカーツールの警告 LNK4217](linker-tools-warning-lnk4217.md)です。 リンカーは、シンボルを参照しているオブジェクトファイルがどの関数であるかを判断できる場合、警告 LNK4286 を生成します。

LNK4286 を解決するには、 `__declspec(dllimport)` *filename_2 .obj* で参照される *シンボル* の事前宣言から宣言修飾子を削除します。

最終的に生成されたコードは正しく動作しますが、インポートされた関数を呼び出すために生成されるコードは、関数を直接呼び出すよりも効率が悪くなります。 この警告は、 [/clr](../../build/reference/clr-common-language-runtime-compilation.md) オプションを使用してコンパイルした場合には表示されません。

データのインポートとエクスポートの宣言の詳細については、「 [dllexport、dllimport](../../cpp/dllexport-dllimport.md)」を参照してください。

## <a name="see-also"></a>関連項目

[リンカーツールの警告 LNK4049](linker-tools-warning-lnk4049.md) \
[リンカーツールの警告 LNK4217](linker-tools-warning-lnk4217.md) \
[dllexport、dllimport](../../cpp/dllexport-dllimport.md)
