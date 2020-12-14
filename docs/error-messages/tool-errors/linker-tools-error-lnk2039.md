---
description: 詳細については、「リンカツール Error LNK2039」を参照してください。
title: リンカ ツール エラー LNK2039
ms.date: 11/04/2016
f1_keywords:
- LNK2039
helpviewer_keywords:
- LNK2039
ms.assetid: eaa296bd-4901-41f6-8410-6d03ee827144
ms.openlocfilehash: 34bddbd456e8e588ff6f7818d8db1d3522ccd06a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97275634"
---
# <a name="linker-tools-error-lnk2039"></a>リンカ ツール エラー LNK2039

別の .obj で定義されている ref クラス ' ' をインポートしています。 \<type> インポートまたは定義する必要がありますが、両方を指定することはできません。

Ref クラス ' <`type`> ' は、指定された .obj ファイルにインポートされますが、別の .obj ファイルでも定義されています。 この状態により、実行時エラーまたはその他の予期しない動作が発生する可能性があります。

### <a name="to-correct-this-error"></a>このエラーを解決するには

1. ' `type` ' が他の .obj ファイルで定義されている必要があるかどうかを確認し、winmd ファイルからインポートする必要があるかどうかを確認します。

1. 定義またはインポートのいずれかを削除します。

## <a name="see-also"></a>関連項目

[リンカーツールのエラーと警告](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)<br/>
[リンカツールエラー LNK1332](../../error-messages/tool-errors/linker-tools-error-lnk1332.md)
