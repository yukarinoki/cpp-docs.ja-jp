---
description: 遅延読み込みヘルパー関数の詳細情報
title: 遅延読み込みヘルパー関数について
ms.date: 01/19/2021
helpviewer_keywords:
- delayed loading of DLLs, helper function
- __delayLoadHelper2 function
- delayimp.lib
- __delayLoadHelper function
- delayhlp.cpp
- delayimp.h
- helper functions
ms.openlocfilehash: a4b25a51af25458f5add5ed7eb3fd58f759dae7b
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "98667247"
---
# <a name="understand-the-delay-load-helper-function"></a>遅延読み込みヘルパー関数について

リンカーでサポートされる遅延読み込みのヘルパー関数は、実行時に実際に DLL を読み込むものです。 ヘルパー関数を変更して、その動作をカスタマイズすることができます。では、指定されたヘルパー関数を使用する代わりに *`delayimp.lib`* 、独自の関数を記述し、プログラムにリンクします。 1つのヘルパー関数は、遅延読み込みされたすべての Dll に対して機能します。

DLL またはインポートの名前に基づいて特定の処理を実行する場合は、独自のバージョンのヘルパー関数を指定できます。

ヘルパー関数は、次のアクションを実行します。

- 既に読み込まれているかどうかを確認するために、格納されているハンドルをライブラリに対してチェックします。

- `LoadLibrary`DLL の読み込みを試行するための呼び出し

- `GetProcAddress`を呼び出して、プロシージャのアドレスを取得します。

- 現在読み込まれているエントリポイントを呼び出すために、遅延インポート読み込みサンクに戻ります。

ヘルパー関数は、次の各アクションの後で、プログラム内の通知フックにコールバックできます。

- ヘルパー関数の開始時

- `LoadLibrary`ヘルパー関数でが呼び出される直前

- `GetProcAddress`ヘルパー関数でが呼び出される直前

- `LoadLibrary`ヘルパー関数でのの呼び出しが失敗した場合

- `GetProcAddress`ヘルパー関数でのの呼び出しが失敗した場合

- ヘルパー関数の処理が完了した後

これらのフックポイントは、遅延インポート読み込みサンクに戻る以外は、何らかの方法でヘルパールーチンの通常の処理を変更する値を返すことができます。

既定のヘルパーコードは *`Delayhlp.cpp`* と *`Delayimp.h`* (vc ディレクトリ内) にあり、 *`include`* (vc ディレクトリ内の) にコンパイルされ *`Delayimp.lib`* *`lib`* ます。 独自のヘルパー関数を記述しない限り、このライブラリをコンパイルに含める必要があります。

次の記事では、ヘルパー関数について説明します。

- [Visual C++ 6.0 以降の DLL 遅延読み込みヘルパー関数の変更点](changes-in-the-dll-delayed-loading-helper-function-since-visual-cpp-6-0.md)

- [呼び出し規則、パラメーター、および戻り値の型](calling-conventions-parameters-and-return-type.md)

- [構造体と定数の定義](structure-and-constant-definitions.md)

- [必要な値の計算](calculating-necessary-values.md)

- [遅延読み込みされた DLL の明示的なアンロード](explicitly-unloading-a-delay-loaded-dll.md)

## <a name="see-also"></a>こちらもご覧ください

[リンカーによる DLL の遅延読み込み](linker-support-for-delay-loaded-dlls.md)
