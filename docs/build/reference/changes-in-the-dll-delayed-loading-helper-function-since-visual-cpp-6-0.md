---
title: 遅延読み込みヘルパー関数を Visual C 6.0 以降の DLL 内の変更 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- delayed loading of DLLs, what's changed
- PFromRva method
- __delayLoadHelper2 function
- helper functions, what's changed
ms.assetid: 99f0be69-105d-49ba-8dd5-3be7939c0c72
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3af68e5ba92a96502e295e75520cd182b4633dae
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="changes-in-the-dll-delayed-loading-helper-function-since-visual-c-60"></a>Visual C++ 6.0 以降の DLL 遅延読み込みヘルパー関数の変更点
コンピューターに複数のバージョンの Visual C が場合や、独自のヘルパー関数を定義した場合、による影響は、DLL に加えられた変更の遅延読み込みヘルパー関数。 例えば:  
  
-   **_ _delayloadhelper**現在 **_ _delayloadhelper2**  
  
-   **__pfnDliNotifyHook**現在 **__pfnDliNotifyHook2**  
  
-   **__pfnDliFailureHook**現在 **__pfnDliFailureHook2**  
  
-   **__FUnloadDelayLoadedDLL**現在 **__FUnloadDelayLoadedDLL2**  
  
> [!NOTE]
>  既定のヘルパー関数を使用している場合は、これらの変更は影響しません。 リンカーの起動方法の変更はありません。  
  
## <a name="multiple-versions-of-visual-c"></a>複数のバージョンの Visual C  
 コンピューターに複数のバージョンの Visual C があれば、リンカーは、delayimp.lib と一致することを確認します。 不一致がある場合、リンカー エラーのいずれかのレポートが表示されます`___delayLoadHelper2@8`または`___delayLoadHelper@8`未解決の外部シンボルとして。 前者の意味を古い delayimp.lib 新しいリンカーし、後者に新しい delayimp.lib を古いリンカーのことを意味します。  
  
 未解決のリンカー エラーが発生した場合は、実行[dumpbin/linkermember](../../build/reference/linkermember.md): を表示するヘルパー関数が代わりに定義されているヘルパー関数を含むと想定している delayimp.lib に 1 です。 ヘルパー関数は、オブジェクト ファイルで定義することも可能性があります。実行[dumpbin/symbols](../../build/reference/symbols.md)を探します.`delayLoadHelper(2)`です。  
  
 わかっている場合、Visual C 6.0 リンカーがあります。  
  
-   Dumpbin 遅延読み込みヘルパーの .lib ファイルや .obj ファイルを定義するかどうかを決定する上で実行 **_ _delayloadhelper2**です。 それ以外の場合は、リンクは失敗します。  
  
-   定義 **_ _delayloadhelper**遅延読み込みヘルパーの .lib ファイルまたは .obj ファイル。  
  
## <a name="user-defined-helper-function"></a>ユーザー定義のヘルパー関数  
 独自のヘルパー関数を定義し、現在のバージョンの Visual C を使用している場合は、次の操作を行います。  
  
-   ヘルパー関数の名前を変更 **_ _delayloadhelper2**です。  
  
-   相対アドレス (Rva) が両方の 32 ビットおよび 64 ビット プログラムで想定どおりに動作するには、遅延記述子 (delayimp.h で ImgDelayDescr) でポインターを絶対アドレス (VAs) から変更されている、ために、これらをポインターに変換する必要があります。 新しい関数が導入されています: PFromRva、delayhlp.cpp で見つかりました。 それぞれの記述子フィールドのこの関数を使用すると、それらをいずれかの 32 ビットまたは 64 ビット ポインターに変換します。 既定の遅延読み込みヘルパー関数引き続き例として使用する適切なテンプレートです。  
  
## <a name="load-all-imports-for-a-delay-loaded-dll"></a>遅延読み込みした DLL のすべてのインポートを読み込む  
 リンカーは、遅延読み込みをするように指定した DLL からすべてのインポートを読み込むことができます。 参照してください[読み込みインポートはすべて、「](../../build/reference/loading-all-imports-for-a-delay-loaded-dll.md)詳細についてはします。  
  
## <a name="see-also"></a>関連項目  
 [ヘルパー関数について](understanding-the-helper-function.md)