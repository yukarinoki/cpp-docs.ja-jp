---
title: リンカー ツールの警告 LNK4286
ms.date: 04/15/2019
f1_keywords:
- LNK4286
helpviewer_keywords:
- LNK4286
ms.openlocfilehash: d0205ba065f6e410383c38a0f1c2eaa0da55fe93
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80173869"
---
# <a name="linker-tools-warning-lnk4286"></a>リンカー ツールの警告 LNK4286

> '*filename_1. .obj*' で定義されたシンボル '*symbol*' は '*filename_2 .obj*' によってインポートされます

シンボルが同じイメージ内のオブジェクトファイル*filename_1*で定義されている場合でも、*シンボル*に[__declspec (dllimport)](../../cpp/dllexport-dllimport.md)が指定されました。 この警告を解決するには、`__declspec(dllimport)` 修飾子を削除します。

## <a name="remarks"></a>解説

Warning LNK4286 は、より一般的なバージョンの[リンカーツールの警告 LNK4217](linker-tools-warning-lnk4217.md)です。 リンカーは、シンボルを参照しているオブジェクトファイルがどの関数であるかを判断できる場合、警告 LNK4286 を生成します。

LNK4286 を解決するには、 *filename_2*で参照される*シンボル*の事前宣言から `__declspec(dllimport)` 宣言修飾子を削除します。

最終的に生成されたコードは正しく動作しますが、インポートされた関数を呼び出すために生成されるコードは、関数を直接呼び出すよりも効率が悪くなります。 この警告は、 [/clr](../../build/reference/clr-common-language-runtime-compilation.md)オプションを使用してコンパイルした場合には表示されません。

データのインポートとエクスポートの宣言の詳細については、「 [dllexport、dllimport](../../cpp/dllexport-dllimport.md)」を参照してください。

## <a name="see-also"></a>参照

[リンカーツールの警告 LNK4049](linker-tools-warning-lnk4049.md) \
[リンカーツールの警告 LNK4217](linker-tools-warning-lnk4217.md) \
[dllexport、dllimport](../../cpp/dllexport-dllimport.md)
