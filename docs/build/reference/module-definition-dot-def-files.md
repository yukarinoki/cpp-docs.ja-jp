---
title: モジュール定義 (.def) ファイル
ms.date: 11/04/2016
helpviewer_keywords:
- def files
- module definition files
- .def files
ms.assetid: 08c0bc28-c5d2-47aa-9624-7fc68bcaa4d8
ms.openlocfilehash: 041894fa88527061d90399540bc29762bff66f81
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57424536"
---
# <a name="module-definition-def-files"></a>モジュール定義 (.def) ファイル

モジュール定義 (.def) ファイルは、エクスポート、属性、およびその他の情報をリンクできるプログラムの詳細については、リンカーを提供します。 .Def ファイルは、DLL を構築する際に最も役立ちます。 あるため、[リンカー オプション](../../build/reference/linker-options.md)使用できるモジュール定義ステートメントではなく .def ファイルは通常必要ありません。 使用することも[方式](../../build/exporting-from-a-dll-using-declspec-dllexport.md)エクスポートされた関数を指定する方法として。

リンカーのフェーズ中に .def ファイルを呼び出すことができます、 [/DEF (モジュール定義ファイルの指定)](../../build/reference/def-specify-module-definition-file.md)リンカー オプション。

エクスポートを持たない .exe ファイルを作成する場合、.def ファイルを使用すると、出力ファイルの大規模かつ低速の読み込みが作成されます。

例については、次を参照してください。 [DEF ファイルを使用する DLL からエクスポート](../../build/exporting-from-a-dll-using-def-files.md)します。

詳細については、次のセクションを参照してください。

- [モジュール定義ステートメントに関する規則](../../build/reference/rules-for-module-definition-statements.md)

- [エクスポート](../../build/reference/exports.md)

- [ヒープサイズ](../../build/reference/heapsize.md)

- [ライブラリ](../../build/reference/library.md)

- [NAME](../../build/reference/name-c-cpp.md)

- [セクション](../../build/reference/sections-c-cpp.md)

- [スタックサイズ](../../build/reference/stacksize.md)

- [スタブ](../../build/reference/stub.md)

- [バージョン](../../build/reference/version-c-cpp.md)

- [予約語](../../build/reference/reserved-words.md)

## <a name="see-also"></a>関連項目

[C/C++ ビルドのリファレンス](../../build/reference/c-cpp-building-reference.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)
