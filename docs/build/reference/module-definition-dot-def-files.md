---
title: モジュール定義 (します。Def) ファイル |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- def files
- module definition files
- .def files
ms.assetid: 08c0bc28-c5d2-47aa-9624-7fc68bcaa4d8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f04035f3c5f0acd77fc197cbef3d2ab507feb0d4
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45710191"
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