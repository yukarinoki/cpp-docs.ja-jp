---
description: 詳細については、ATL プロジェクトでの CRT へのリンクに関するページを参照してください。
title: ATL プロジェクトで CRT にリンクする
ms.date: 11/04/2016
helpviewer_keywords:
- CRT, linking with ATL
- WinMainCRTStartup method
- DllMainCRTStartup method
- wWinMainCRTStartup method
- ATL, C Run-Time library (CRT)
ms.assetid: 650957ae-362c-4ecf-8b03-5d49138e8b5b
ms.openlocfilehash: e54301332d9a83546e41ab42169f06d305bbc6a2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147629"
---
# <a name="linking-to-the-crt-in-your-atl-project"></a>ATL プロジェクトで CRT にリンクする

[C Run-Time ライブラリ](../c-runtime-library/crt-library-features.md)(CRT) には、ATL 開発中にプログラミングをはるかに簡単にするための便利な関数が多数用意されています。 すべての ATL プロジェクトは、CRT ライブラリにリンクします。 リンク方法の利点と欠点については、「 [CRT へのリンクに使用されるメソッドの利点とトレードオフ](../atl/benefits-and-tradeoffs-of-the-method-used-to-link-to-the-crt.md)」を参照してください。

## <a name="effects-of-linking-to-the-crt-on-your-program-image"></a>プログラムイメージで CRT にリンクした場合の影響

CRT に静的にリンクしている場合、CRT からのコードは実行可能イメージに配置されるため、イメージを実行するためにシステム上に CRT DLL が存在している必要はありません。 CRT に動的にリンクする場合、CRT DLL 内のコードへの参照はイメージに配置されますが、コード自体は配置されません。 特定のシステムでイメージを実行するには、そのシステム上に CRT DLL が存在している必要があります。 CRT に動的にリンクする場合でも、一部のコードが静的にリンクされている可能性があります (たとえば、 `DllMainCRTStartup` )。

イメージをリンクするときは、イメージの読み込み後にオペレーティングシステムが呼び出すエントリポイントを明示的または暗黙的に指定します。 DLL の場合、既定のエントリポイントはに `DllMainCRTStartup` なります。 EXE の場合は、になり `WinMainCRTStartup` ます。 既定値は/ENTRY リンカーオプションを使用してオーバーライドできます。 CRT は `DllMainCRTStartup` 、、 `WinMainCRTStartup` 、および (実行可能 `wWinMainCRTStartup` ファイルの Unicode エントリポイント) の実装を提供します。 これらの CRT によって提供されるエントリポイントは、グローバルオブジェクトのコンストラクターを呼び出し、一部の CRT 関数によって使用されるその他のデータ構造体を初期化します。 このスタートアップコードは、25,000 が静的にリンクされている場合、イメージに追加します。 動的にリンクされている場合、ほとんどのコードは DLL 内にあるため、イメージのサイズは小さくなります。

詳細については、リンカーのトピック「 [/entry (エントリポイントシンボル)](../build/reference/entry-entry-point-symbol.md)」を参照してください。

## <a name="optimization-options"></a>最適化オプション

リンカーオプション/OPT: NOWIN98 を使用すると、Windows 98 システムでの読み込み時間の増加を犠牲にして、既定の ATL コントロールを10K でさらに減らすことができます。 リンクオプションの詳細については、「 [/opt (最適化)](../build/reference/opt-optimizations.md)」を参照してください。

## <a name="see-also"></a>関連項目

[ATL および C Run-Time コードを使用したプログラミング](../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[DLL と Visual C++ ランタイム ライブラリの動作](../build/run-time-library-behavior.md)
