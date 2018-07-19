---
title: EDITBIN オプション |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- editbin
dev_langs:
- C++
helpviewer_keywords:
- EDITBIN program, options
ms.assetid: 2da9f88e-cbab-4d64-bb66-ef700535230f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1922e410b0151337ce403e24d20ae90b7e964cd5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378523"
---
# <a name="editbin-options"></a>EDITBIN オプション
EDITBIN を使用して、オブジェクト ファイル、実行可能ファイル、およびダイナミック リンク ライブラリ (Dll) を変更することができます。 オプションは、EDITBIN に加える変更を指定します。  
  
 オプションは、ダッシュ (-) またはスラッシュ (/)、オプションの名前を続けて、オプション指定子で構成されます。 オプション名の省略形は使用できません。 いくつかのオプションは、コロン (:) の後ろに指定されている引数を受け取ります。 1 つのオプションの指定には、スペースやタブは挿入できません。 複数のオプションを指定する場合は、各オプションを 1 つ以上のスペースまたはタブで区切ります。 オプション名およびそのキーワード引数やファイル名の引数は、大文字小文字を区別します。 たとえば、- バインドと/BIND には、同じことを意味します。  
  
 EDITBIN では、次のオプションがあります。  
  
|オプション|目的|  
|------------|-------------|  
|[/ALLOWBIND](../../build/reference/allowbind.md)|DLL をバインドできるかどうかを指定します。|  
|[/ALLOWISOLATION](../../build/reference/allowisolation.md)|DLL または実行可能ファイル マニフェスト検索の動作を指定します。|  
|[/APPCONTAINER](../../build/reference/appcontainer.md)|アプリを AppContainer 内で実行する必要があるかどうかを指定します: UWP アプリなどです。|  
|[/BIND](../../build/reference/bind.md)|速度の読み込み時に指定されたオブジェクト内のエントリ ポイントのアドレスを設定します。|  
|[/DYNAMICBASE](../../build/reference/dynamicbase.md)|かどうか、DLL または実行可能イメージにランダムにリベースできる読み込み時にアドレス space layout randomization (機能) を使用して、指定します。|  
|[/ERRORREPORT](../../build/reference/errorreport-editbin-exe.md)|Microsoft に内部エラーを報告します。|  
|[/HEAP](../../build/reference/heap.md)|実行可能イメージのヒープのサイズをバイト単位で設定します。|  
|[/HIGHENTROPYVA](../../build/reference/highentropyva.md)|DLL または実行可能イメージが高エントロピ (64 ビット) のアドレス空間 ASLR (layout randomization) をサポートするかどうかを指定します。|  
|[/INTEGRITYCHECK](../../build/reference/integritycheck.md)|読み込み時にデジタル署名を確認するかどうかを指定します。|  
|[/LARGEADDRESSAWARE](../../build/reference/largeaddressaware.md)|オブジェクトが 2 ギガバイトを超えるアドレスをサポートしているかどうかを指定します。|  
|[/NOLOGO](../../build/reference/nologo-editbin.md)|EDITBIN 開始メッセージを抑制します。|  
|[/NXCOMPAT](../../build/reference/nxcompat.md)|実行可能イメージは Windows データ実行防止と互換性があるかどうかを指定します。|  
|[/REBASE](../../build/reference/rebase.md)|指定したオブジェクトのベース アドレスを設定します。|  
|[/RELEASE](../../build/reference/release.md)|ヘッダーにチェックサムを設定します。|  
|[/SECTION](../../build/reference/section-editbin.md)|セクションの属性をオーバーライドします。|  
|[/STACK](../../build/reference/stack.md)|実行可能イメージのスタックのサイズをバイト単位で設定します。|  
|[/SUBSYSTEM](../../build/reference/subsystem.md)|実行環境を指定します。|  
|[/SWAPRUN](../../build/reference/swaprun.md)|実行可能イメージのスワップ ファイルにコピーし、し、そこから実行する必要がありますを指定します。|  
|[/TSAWARE](../../build/reference/tsaware.md)|マルチ ユーザー環境で実行するアプリが設計されているを指定します。|  
|[/VERSION](../../build/reference/version.md)|ヘッダーにバージョン番号を設定します。|  
  
## <a name="see-also"></a>関連項目  
 [C/C++ ビルド ツール](../../build/reference/c-cpp-build-tools.md)   
 [EDITBIN リファレンス](../../build/reference/editbin-reference.md)