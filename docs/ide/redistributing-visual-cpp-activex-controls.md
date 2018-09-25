---
title: Visual C++ ActiveX コントロールの再頒布 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], redistributing
- controls [C++], distributing
ms.assetid: eefbb7e4-d28c-4c35-98bf-d9540cfaae83
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5eea5ef50427e7398246d8da3d7977bb714d9b54
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46383884"
---
# <a name="redistributing-visual-c-activex-controls"></a>Visual C++ ActiveX コントロールの再配布

Visual C++ 6.0 には、アプリケーションで使用できてその後再配布する ActiveX コントロールが用意されています。 このようなコントロールは Visual C++ には含まれなくなりました。 Visual C++ 6.0 のライセンス契約に基づき、Visual C++ で開発されたアプリケーションでこれらのコントロールを再配布できます。

> [!NOTE]
>  Microsoft では、Visual C++ 6.0 のサポートを終了しています。

再配布可能な Visual C++ 6.0 ActiveX コントロールの一覧については、Visual C++ 6.0 プロダクト CD のディスク 1 に含まれる Common\Redist\Redist.txt を参照してください。

アプリケーションを配布するとき、ActiveX コントロールの .ocx をインストールし、登録する必要があります (Regsvr32.exe を使用)。 また、対象のコンピューターに次のシステム ファイルの最新版が含まれている必要があります (アスタリスクはファイルを登録する必要があることを示します)。

- Asycfilt.dll

- Comcat.dll \*

- Oleaut32.dll \*

- Olepro32.dll \*

- Stdole2.tlb

対象のシステムでこれらの DLL が利用できない場合、該当オペレーティング システムを更新するための所定のメカニズムを利用して更新する必要があります。 Windows オペレーティング システムの最新サービス パックは [http://windowsupdate.microsoft.com](http://windowsupdate.microsoft.com) からダウンロードできます。

データベースに接続する ActiveX コントロールを使用するとき、対象のコンピューターでデータ ソース名を複製する必要もあります。 複製は、`ConfigDSN` などの関数を使用してプログラムで行うことができます。

一部の再配布可能 ActiveX コントロールでは、依存関係がさらに増えます。 Visual C++ 6.0 プロダクト CD の OS\システム フォルダーにある .ocx ファイルごとに .dep ファイルもあります。 再配布する .ocx ファイルごとに、それに対応する .dep ファイルで 1 つまたは複数の USES エントリを探してください。 ファイルが一覧表示されている場合、ファイルが対象のコンピューターにあることを確認する必要があります。 .ocx ファイルを直接サポートする DLL はすべて登録する必要があります。 (Regsvr32.exe を正常に実行するには、コントロールによって静的に読み込まれるすべての DLL が対象のコンピューターに含まれている必要があります。)さらに、依存関係として一覧表示されている DLL に Visual C++ 6.0 CD の OS/システム フォルダーの .dep ファイルも含まれている場合、その .dep ファイルでも USES エントリを探す必要があります。

## <a name="see-also"></a>参照

[Visual C++ ファイルの再配布](../ide/redistributing-visual-cpp-files.md)