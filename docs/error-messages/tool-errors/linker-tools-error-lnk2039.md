---
title: リンカ ツール エラー LNK2039 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2039
dev_langs:
- C++
helpviewer_keywords:
- LNK2039
ms.assetid: eaa296bd-4901-41f6-8410-6d03ee827144
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ac4fdde90911427a1a193bfb6f3a950a7bdcf180
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46081794"
---
# <a name="linker-tools-error-lnk2039"></a>リンカ ツール エラー LNK2039

ref クラスをインポートする\<型 >' another.obj で定義されているは、インポートまたは定義されている、両方が可能にする必要があります

Ref クラス ' <`type`>' が指定された .obj ファイルにインポートされますが、別の .obj ファイルにも定義されています。 この条件には、実行時エラーまたはその他の予期しない動作可能性があります。

### <a name="to-correct-this-error"></a>このエラーを解決するには

1. 確認するかどうか '`type`' その他の .obj ファイルで定義する必要があり、.winmd ファイルからインポートする必要があるかどうかを確認します。

1. 定義またはインポートのいずれかを削除します。

## <a name="see-also"></a>関連項目

[リンカー ツール エラーと警告](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)<br/>
[リンカー ツール エラー LNK1332](../../error-messages/tool-errors/linker-tools-error-lnk1332.md)