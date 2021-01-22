---
description: 遅延読み込みされたインポートのバインドについての詳細情報
title: 遅延読み込みされたインポートのバインド
ms.date: 01/19/2021
helpviewer_keywords:
- /DELAY:NOBIND linker option
- DELAY:NOBIND linker option
ms.openlocfilehash: 49d321a30eeb3ab12ec832fb86a662f2035e1e3a
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "98666941"
---
# <a name="bind-delay-loaded-imports"></a>遅延読み込みされたインポートのバインド

既定のリンカー動作では、遅延読み込みされた DLL に対して、バインド可能なインポートアドレステーブル (IAT) が作成されます。 DLL がバインドされている場合、ヘルパー関数は、参照される各インポートでを呼び出すのではなく、バインドされた情報を使用しようとし `GetProcAddress` ます。 タイムスタンプまたは優先アドレスが、読み込まれている DLL 内のアドレスと一致しない場合、ヘルパー関数はバインドされたインポートアドレステーブルが古くなっているものと見なします。 この処理は、IAT が存在しない場合と同様に行われます。

DLL の遅延読み込みされたインポートをバインドしない場合は、 [`/delay:nobind`](delay-delay-load-import-settings.md) リンカーのコマンドラインでを指定します。 リンカーは、バインドされたインポートアドレステーブルを生成しません。これにより、イメージファイルの領域が節約されます。

## <a name="see-also"></a>こちらもご覧ください

[リンカーによる DLL の遅延読み込み](linker-support-for-delay-loaded-dlls.md)
