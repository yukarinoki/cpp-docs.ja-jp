---
description: '詳細情報: C 言語の実行形式で使う C++ 関数のエクスポート'
title: C 言語の実行形式で使う C++ 関数のエクスポート
ms.date: 11/04/2016
helpviewer_keywords:
- functions [C++], C++ functions in C executables
- exporting DLLs [C++], C++ functions in C executables
- exporting functions [C++], C++ functions in C executables
- functions [C++], exporting
ms.assetid: 80b9e982-f52d-4312-a891-f73cc69f3c2b
ms.openlocfilehash: c11ee56afb6fc99dbdf5a795cb8551e54835cd67
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97156620"
---
# <a name="exporting-c-functions-for-use-in-c-language-executables"></a>C 言語の実行形式で使う C++ 関数のエクスポート

C++ で記述された DLL 内の関数に C 言語のモジュールからアクセスするには、C++ リンケージではなく C リンケージを使って関数を宣言する必要があります。 特に指定しない限り、C++ コンパイラは C++ のタイプ セーフな名前付け規約 (名前の装飾) と C++ の呼び出し規則を使います。C++ の規約を使うと、C からの呼び出しが難しくなります。

C リンケージを指定するには、関数の宣言に `extern "C"` を指定します。 次に例を示します。

```
extern "C" __declspec( dllexport ) int MyFunc(long parm1);
```

## <a name="what-do-you-want-to-do"></a>実行する操作

- [.def ファイルを使用した DLL からのエクスポート](exporting-from-a-dll-using-def-files.md)

- [__declspec(dllexport) を使用して DLL からエクスポートする](exporting-from-a-dll-using-declspec-dllexport.md)

- [AFX_EXT_CLASS を使用したエクスポートとインポート](exporting-and-importing-using-afx-ext-class.md)

- [C または C++ 言語の実行可能ファイルで使用する C 関数のエクスポート](exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [エクスポート方式の使い分け](determining-which-exporting-method-to-use.md)

- [__declspec(dllimport) を使用してアプリケーションにインポートする](importing-into-an-application-using-declspec-dllimport.md)

- [DLL の初期化](run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [装飾名](reference/decorated-names.md)

- [extern を使用したリンケージの指定](../cpp/extern-cpp.md)

## <a name="see-also"></a>関連項目

[DLL からのエクスポート](exporting-from-a-dll.md)
