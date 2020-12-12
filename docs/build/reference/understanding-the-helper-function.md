---
description: '詳細情報: ヘルパー関数について'
title: ヘルパー関数について
ms.date: 11/04/2016
helpviewer_keywords:
- delayed loading of DLLs, helper function
- __delayLoadHelper2 function
- delayimp.lib
- __delayLoadHelper function
- delayhlp.cpp
- delayimp.h
- helper functions
ms.assetid: 6279c12c-d908-4967-b0b3-cabfc3e91d3d
ms.openlocfilehash: d47e392d78d6cf872af28b992885c57d34bddf0f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247099"
---
# <a name="understanding-the-helper-function"></a>ヘルパー関数について

リンカーによってサポートされる遅延読み込みのヘルパー関数は、実行時に DLL を実際に読み込むものです。 ヘルパー関数を変更して独自の関数を記述し、それをプログラムにリンクすることで、その動作をカスタマイズできます。これは、指定されたヘルパー関数を使用する代わりに、プログラムにリンクします。 1つのヘルパー関数は、遅延読み込みされたすべての Dll に対して機能します。

DLL またはインポートの名前に基づいて特定の処理を実行する場合は、独自のバージョンのヘルパー関数を指定できます。

ヘルパー関数は、次のアクションを実行します。

- 既に読み込まれているかどうかを確認するために、格納されているハンドルをライブラリに対してチェックします。

- DLL の読み込みを試行するために **LoadLibrary** を呼び出します

- **GetProcAddress** を呼び出して、プロシージャのアドレスを取得します。

- 現在読み込まれているエントリポイントを呼び出すために、遅延インポート読み込みサンクに戻ります。

ヘルパー関数は、次の各アクションの後で、プログラム内の通知フックにコールバックできます。

- ヘルパー関数の開始時

- ヘルパー関数で **LoadLibrary** が呼び出される直前

- ヘルパー関数で **GetProcAddress** が呼び出される直前

- ヘルパー関数の **LoadLibrary** の呼び出しが失敗した場合

- ヘルパー関数での **GetProcAddress** の呼び出しが失敗した場合

- ヘルパー関数の処理が完了した後

これらのフックポイントは、遅延インポート読み込みサンクに戻る以外の方法でヘルパールーチンの通常の処理を変更する値を返すことができます。

既定のヘルパーコードは、Delayhlp と Delayhlp. h (vci インクルード) にあり、Delayhlp. lib (vc¥ lib) でコンパイルされます。 独自のヘルパー関数を記述しない限り、このライブラリをコンパイルに含める必要があります。

次のトピックでは、ヘルパー関数について説明します。

- [Visual C++ 6.0 以降の DLL 遅延読み込みヘルパー関数の変更](changes-in-the-dll-delayed-loading-helper-function-since-visual-cpp-6-0.md)

- [呼び出し規約、パラメーター、および戻り値の型](calling-conventions-parameters-and-return-type.md)

- [構造体と定数の定義](structure-and-constant-definitions.md)

- [必要な値の計算](calculating-necessary-values.md)

- [Delay-Loaded DLL のアンロード](explicitly-unloading-a-delay-loaded-dll.md)

## <a name="see-also"></a>関連項目

[リンカーによる Delay-Loaded Dll のサポート](linker-support-for-delay-loaded-dlls.md)
