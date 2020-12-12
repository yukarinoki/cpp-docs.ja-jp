---
description: 詳細については、「バインドインポート」を参照してください。
title: インポートのバインド
ms.date: 11/04/2016
helpviewer_keywords:
- /DELAY:NOBIND linker option
- DELAY:NOBIND linker option
ms.assetid: bb766038-deb1-41b1-bcbc-29a30e8c1e2a
ms.openlocfilehash: 7d1b4374bf1d3340a918f252d80102057febe053
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182711"
---
# <a name="binding-imports"></a>インポートのバインド

既定のリンカー動作では、遅延読み込みされた DLL のバインド可能なインポートアドレステーブルが作成されます。 DLL がバインドされている場合、ヘルパー関数は、参照される各インポートで **GetProcAddress** を呼び出す代わりに、バインドされた情報を使用しようとします。 タイムスタンプまたは優先するアドレスが、読み込まれている DLL のアドレスと一致しない場合、ヘルパー関数はバインドされたインポートアドレステーブルが古くなっていると想定し、存在しないかのように処理を続行します。

DLL の遅延読み込みのインポートをバインドしない場合は、リンカーのコマンドラインで [/delay](delay-delay-load-import-settings.md): nobind を指定すると、バインドされたインポートアドレステーブルが生成されず、イメージファイル内の領域が消費されなくなります。

## <a name="see-also"></a>関連項目

[リンカーによる Delay-Loaded Dll のサポート](linker-support-for-delay-loaded-dlls.md)
