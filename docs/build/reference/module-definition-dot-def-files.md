---
description: 詳細については、Module-Definition () を参照してください。Def) ファイル
title: モジュール定義 (.def) ファイル
ms.date: 11/04/2016
helpviewer_keywords:
- def files
- module definition files
- .def files
ms.assetid: 08c0bc28-c5d2-47aa-9624-7fc68bcaa4d8
ms.openlocfilehash: d52141a2917b2c82616597b2d070a84b96d1a653
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97137814"
---
# <a name="module-definition-def-files"></a>モジュール定義 (.def) ファイル

モジュール定義 (.def) ファイルは、リンクするプログラムに関するエクスポート、属性、およびその他の情報に関する情報をリンカーに提供します。 .Def ファイルは、DLL をビルドするときに最も役立ちます。 モジュール定義ステートメントの代わりに使用できる [MSVC リンカーオプション](linker-options.md) があるため、.def ファイルは通常必要ありません。 エクスポートされた関数を指定する方法として、 [__declspec (dllexport)](../exporting-from-a-dll-using-declspec-dllexport.md) を使用することもできます。

リンカーフェーズ中に、 [/def (Module-Definition ファイルの指定)](def-specify-module-definition-file.md) リンカーオプションを使用して、.def ファイルを呼び出すことができます。

エクスポートのない .exe ファイルをビルドする場合、.def ファイルを使用すると、出力ファイルのサイズが大きくなり、読み込みが遅くなります。

例については、「 [DEF ファイルを使用した DLL からのエクスポート](../exporting-from-a-dll-using-def-files.md)」を参照してください。

詳しくは、以下のセクションをご覧ください。

- [Module-Definition ステートメントの規則](rules-for-module-definition-statements.md)

- [エクスポート](exports.md)

- [HEAPSIZE](heapsize.md)

- [ライブラリ](library.md)

- [名前](name-c-cpp.md)

- [各項](sections-c-cpp.md)

- [STACKSIZE](stacksize.md)

- [スタブ](stub.md)

- [VERSION](version-c-cpp.md)

- [予約語](reserved-words.md)

## <a name="see-also"></a>関連項目

[C/C++ ビルドのリファレンス](c-cpp-building-reference.md)<br/>
[MSVC リンカー オプション](linker-options.md)
