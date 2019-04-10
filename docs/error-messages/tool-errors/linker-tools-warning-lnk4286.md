---
title: リンカー ツールの警告 LNK4286
ms.date: 04/09/2019
f1_keywords:
- LNK4286
helpviewer_keywords:
- LNK4286
ms.openlocfilehash: f4ab9104c68534eaf1278a6cacb91623c24a237b
ms.sourcegitcommit: 0ad3f4517e64900a2702dd3d366586f9e2bce2c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/10/2019
ms.locfileid: "59477635"
---
# <a name="linker-tools-warning-lnk4286"></a>リンカー ツールの警告 LNK4286

> シンボル '*シンボル*'で定義されている'*filename_1.obj*'によってインポートされる'*filename_2.obj*'

[_declspec](../../cpp/dllexport-dllimport.md)が指定されました*シンボル*オブジェクト ファイルでシンボルが定義されている場合でも*filename_1.obj*で同じイメージ。 削除、`__declspec(dllimport)`修飾子をこの警告を解決します。

## <a name="remarks"></a>Remarks

警告 LNK4286 がより一般的なバージョンの[リンカー ツールの警告 LNK4217](linker-tools-warning-lnk4217.md)します。 リンカーでは、オブジェクト ファイルの参照、シンボルがない関数に通知されることと、警告 LNK4286 が生成されます。

LNK4286 を解決するには、削除、`__declspec(dllimport)`の事前宣言から宣言修飾子*シンボル*で参照される*filename_2.obj*します。

最終的に生成されたコードが正しく動作しますが、インポートされた関数を呼び出す生成されたコードは、関数を直接呼び出すよりも非効率です。 使用してコンパイルするときに、この警告は表示されない、 [/clr](../../build/reference/clr-common-language-runtime-compilation.md)オプション。

詳細については、インポートし、データの宣言をエクスポートを参照してください。 [dllexport、dllimport](../../cpp/dllexport-dllimport.md)します。

## <a name="see-also"></a>関連項目

[リンカー ツールの警告 LNK4049](linker-tools-warning-lnk4049.md) \
[リンカー ツールの警告 LNK4286](linker-tools-warning-lnk4286.md) \
[dllexport、dllimport](../../cpp/dllexport-dllimport.md)