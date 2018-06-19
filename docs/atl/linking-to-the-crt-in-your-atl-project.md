---
title: ATL プロジェクトで CRT にリンク |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- DllMainCRTStartup
- wWinMainCRTStartup
- WinMainCRTStartup
dev_langs:
- C++
helpviewer_keywords:
- CRT, linking with ATL
- WinMainCRTStartup method
- DllMainCRTStartup method
- wWinMainCRTStartup method
- ATL, C Run-Time library (CRT)
ms.assetid: 650957ae-362c-4ecf-8b03-5d49138e8b5b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ec0d93f8770ebbd893491c0e8b8eed239396e00a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32356384"
---
# <a name="linking-to-the-crt-in-your-atl-project"></a>ATL プロジェクトで CRT にリンク
[C ランタイム ライブラリ](../c-runtime-library/crt-library-features.md)(CRT) できるようにするプログラミングはるかに簡単 ATL 開発時に多くの便利な関数を提供します。 すべての ATL プロジェクトは、CRT ライブラリにリンクします。 長所と短所のメソッドのリンクを確認できます[CRT へのリンクに使用されるメソッドの利点とトレードオフ](../atl/benefits-and-tradeoffs-of-the-method-used-to-link-to-the-crt.md)です。  
  
## <a name="effects-of-linking-to-the-crt-on-your-program-image"></a>プログラム イメージ CRT にリンクの効果  
 CRT に静的にリンクする場合は、CRT のコードは、実行可能イメージに配置され、イメージを実行するシステムで、CRT DLL が存在する必要はありません。 CRT に動的にリンクする場合は、CRT DLL 内のコードへの参照が、イメージが、コード自体ではないに配置されます。 イメージを指定したシステムで実行するためには、CRT DLL は、そのシステムに存在する必要があります。 でもを動的にリンクする場合、CRT、いくつかのコードを静的にリンクできるがあります (たとえば、 **DllMainCRTStartup**)。  
  
 イメージをリンクするときに明示的または暗黙的を指定するイメージを読み込んだ後に、オペレーティング システムを呼び出すエントリ ポイント。 既定のエントリ ポイントは、dll の場合、 **DllMainCRTStartup**です。 EXE は**WinMainCRTStartup**です。 /ENTRY リンカー オプションを使用して既定値を上書きすることができます。 CRT の実装を提供する**DllMainCRTStartup**、 **WinMainCRTStartup**、および**wWinMainCRTStartup** (exe ファイルの Unicode のエントリ ポイント)。 これらの CRT に用意されているエントリ ポイントは、グローバル オブジェクトのコンス トラクターを呼び出すし、一部の CRT 関数によって使用されているその他のデータ構造を初期化します。 このスタートアップ コードでは、静的にリンクされている場合、約 25 K を画像に追加します。 動的にリンクされている場合は、イメージのサイズを小さく抑えるために、コードのほとんどが、DLL 内です。  
  
 詳細については、リンカーのトピックを参照してください。 [/ENTRY (エントリ ポイント シンボル)](../build/reference/entry-entry-point-symbol.md)です。  
  
## <a name="optimization-options"></a>最適化オプション  
 /OPT:NOWIN98 リンカー オプションを使用してさらに減らせる 10 k は、既定の ATL コントロール譲歩読み込み Windows 98 システムで時間を増加します。 リンク オプションの詳細については、次を参照してください。 [/OPT (最適化)](../build/reference/opt-optimizations.md)です。  
  
## <a name="see-also"></a>関連項目  
 [ATL および C ランタイム コードによるプログラミング](../atl/programming-with-atl-and-c-run-time-code.md)   
 [DLL と Visual C++ ランタイム ライブラリの動作](../build/run-time-library-behavior.md)

