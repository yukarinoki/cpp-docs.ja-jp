---
description: 詳細については、Compiler-Controlled リンクオプションに関するページを参照してください。
title: Compiler-Controlled LINK Options
ms.date: 11/04/2016
helpviewer_keywords:
- LINK tool [C++], compiler-controlled options
- linker [C++], CL compiler control
- linking [C++], affected by CL features
- cl.exe compiler [C++], features that affect linking
- cl.exe compiler [C++], controlling linker
ms.assetid: e4c03896-c99c-4599-8502-e0f4bebe69d0
ms.openlocfilehash: 86f03f53fe19f6788528dca421fb6030289fca99
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97178980"
---
# <a name="compiler-controlled-link-options"></a>Compiler-Controlled LINK Options

/C オプションを指定しない限り、CL コンパイラは LINK を自動的に呼び出します。 CL は、コマンドラインオプションと引数を使用して、リンカーを制御します。 次の表は、リンクに影響を与える CL の機能の概要を示しています。

|CL 仕様|リンクに影響を与える CL アクション|
|----------------------|---------------------------------|
|.C、.cxx、.cpp、.def 以外の任意のファイル名拡張子|ファイル名をリンクに入力として渡します。|
|*ファイル名*. def|/DEF:*filename*. DEF を渡します。|
|/F *番号*|Pass/STACK:*number*|
|/Fd *ファイル名*|/PDB:*filename* を渡します。|
|/Fe *ファイル名*|/OUT:*filename* を渡します。|
|/Fm *ファイル名*|/MAP:*filename* を渡します。|
|/Gy|パッケージ関数 (Comdat) を作成します。関数レベルのリンクを有効にします|
|/LD|/DLL を渡します|
|/LDd|/DLL を渡します|
|/link|コマンドラインの残りの部分をリンクに渡します|
|/MD または/MT|.Obj ファイルに既定のライブラリ名を配置します。|
|/MDd または/MTd|.Obj ファイルに既定のライブラリ名を配置します。 シンボルを定義し **_DEBUG**|
|/nologo|/NOLOGO|
|/Zd|/DEBUG を渡します。|
|/Zi または/Z7|/DEBUG を渡します。|
|/Zl|.Obj ファイルから既定のライブラリ名を省略します|

詳細については、「 [MSVC Compiler Options](compiler-options.md)」を参照してください。

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
