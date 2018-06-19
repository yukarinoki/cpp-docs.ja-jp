---
title: ヘルパー関数について |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- delayed loading of DLLs, helper function
- __delayLoadHelper2 function
- delayimp.lib
- __delayLoadHelper function
- delayhlp.cpp
- delayimp.h
- helper functions
ms.assetid: 6279c12c-d908-4967-b0b3-cabfc3e91d3d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 54ed331022c29ecc47d61bbcccbfac82000cb235
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379238"
---
# <a name="understanding-the-helper-function"></a>ヘルパー関数について
リンカーでサポートされているに遅延読み込み用のヘルパー関数は、実行時に DLL を実際に読み込むです。 独自の関数を作成し、Delayimp.lib で提供されているヘルパー関数を使用する代わりに、プログラムにリンクすることでその動作をカスタマイズするヘルパー関数を変更できます。 1 つのヘルパー関数では、すべての遅延読み込み Dll は機能します。  
  
 DLL またはインポートの名前に基づく特定の処理を実行する場合は、ヘルパー関数のバージョンを提供できます。  
  
 ヘルパー関数では、次の操作を実行します。  
  
-   あるかどうかは、既に読み込まれているを参照してください。 ライブラリに格納されたハンドルを確認します。  
  
-   呼び出し**LoadLibrary** DLL の読み込みを試行するには  
  
-   呼び出し**GetProcAddress**プロシージャのアドレスの取得を試行するには  
  
-   遅延インポートを返します。 読み込みを今すぐに読み込まれたエントリ ポイントを呼び出すサンク  
  
 ヘルパー関数は、次の操作のたびに、プログラムで通知フックをコールバックできます。  
  
-   再起動すると、ヘルパー関数  
  
-   直前に**LoadLibrary**ヘルパー関数で呼び出されます  
  
-   直前に**GetProcAddress**ヘルパー関数で呼び出されます  
  
-   場合に呼び出し**LoadLibrary**ヘルパー関数に失敗しました  
  
-   場合に呼び出し**GetProcAddress**ヘルパー関数に失敗しました  
  
-   ヘルパーした後で、関数が行われる処理  
  
 これらの各フック ポイント遅延インポート ロード サンクを返す以外の何らかの形でヘルパー ルーチンの通常の処理を変更する値を返すことができます。  
  
 既定のヘルパー コードできます Delayhlp.cpp および Delayimp.h (に vc\include) あり vc\lib) の「Delayimp.lib でコンパイルされています。 独自のヘルパー関数を記述しない限り、コンパイル時にこのライブラリをインクルードする必要があります。  
  
 次のトピックでは、ヘルパー関数について説明します。  
  
-   [Visual C++ 6.0 以降の DLL 遅延読み込みヘルパー関数の変更点](../../build/reference/changes-in-the-dll-delayed-loading-helper-function-since-visual-cpp-6-0.md)  
  
-   [呼び出し規約、パラメーター、および戻り値の型](../../build/reference/calling-conventions-parameters-and-return-type.md)  
  
-   [構造体と定数の定義](../../build/reference/structure-and-constant-definitions.md)  
  
-   [必要な値の計算](../../build/reference/calculating-necessary-values.md)  
  
-   [遅延読み込みした DLL のアンロード](../../build/reference/explicitly-unloading-a-delay-loaded-dll.md)  
  
## <a name="see-also"></a>関連項目  
 [リンカーによる DLL の遅延読み込み](../../build/reference/linker-support-for-delay-loaded-dlls.md)