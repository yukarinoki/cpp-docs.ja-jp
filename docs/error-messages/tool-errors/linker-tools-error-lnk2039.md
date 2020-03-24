---
title: リンカ ツール エラー LNK2039
ms.date: 11/04/2016
f1_keywords:
- LNK2039
helpviewer_keywords:
- LNK2039
ms.assetid: eaa296bd-4901-41f6-8410-6d03ee827144
ms.openlocfilehash: 7712747deb865ec62fa007fcd95ad09630d00cea
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194500"
---
# <a name="linker-tools-error-lnk2039"></a>リンカ ツール エラー LNK2039

別の .obj に定義されている ref クラス '\<type > ' をインポートしています。インポートまたは定義する必要がありますが、両方を指定することはできません。

Ref クラス ' <`type`> ' は、指定された .obj ファイルにインポートされますが、別の .obj ファイルでも定義されています。 この状態により、実行時エラーまたはその他の予期しない動作が発生する可能性があります。

### <a name="to-correct-this-error"></a>このエラーを解決するには

1. '`type`' が他の .obj ファイルで定義されている必要があるかどうかを確認し、winmd ファイルからインポートする必要があるかどうかを確認します。

1. 定義またはインポートのいずれかを削除します。

## <a name="see-also"></a>参照

[リンカー ツール エラーと警告](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)<br/>
[リンカー ツール エラー LNK1332](../../error-messages/tool-errors/linker-tools-error-lnk1332.md)
