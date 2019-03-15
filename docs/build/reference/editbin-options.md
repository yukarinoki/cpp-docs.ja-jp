---
title: EDITBIN オプション
ms.date: 11/04/2016
f1_keywords:
- editbin
helpviewer_keywords:
- EDITBIN program, options
ms.assetid: 2da9f88e-cbab-4d64-bb66-ef700535230f
ms.openlocfilehash: e7338c6a45d74aa8efac1b72683cca7661c62e0a
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57820105"
---
# <a name="editbin-options"></a>EDITBIN オプション

EDITBIN を使用して、オブジェクト ファイル、実行可能ファイル、およびダイナミック リンク ライブラリ (Dll) を変更することができます。 オプションは、EDITBIN が加える変更を指定します。

オプションは、ダッシュ (-) またはフォワード スラッシュ (/) の後に、オプションの名前のいずれかである、オプション指定子で構成されます。 オプション名の省略形は使用できません。 いくつかのオプションは、コロン (:) 後に指定した引数を受け取る。 1 つのオプションの指定には、スペースやタブは挿入できません。 複数のオプションを指定する場合は、各オプションを 1 つ以上のスペースまたはタブで区切ります。 オプション名とそのキーワード引数またはファイル名の引数は区別されません。 たとえば、- バインドと/bind」と入力には、同じことを意味します。

EDITBIN には、次のオプションがあります。

|オプション|目的|
|------------|-------------|
|[/ALLOWBIND](allowbind.md)|DLL をバインドできるかどうかを指定します。|
|[/ALLOWISOLATION](allowisolation.md)|DLL または実行可能ファイル マニフェスト検索の動作を指定します。|
|[/APPCONTAINER](appcontainer.md)|アプリを AppContainer 内で実行する必要があるかどうかを指定します。 — たとえば、UWP アプリ。|
|[/BIND](bind.md)|指定したオブジェクトの読み込み時間を短縮するエントリ ポイントのアドレスを設定します。|
|[/DYNAMICBASE](dynamicbase.md)|かどうか、DLL または実行可能イメージにランダムに再ベースできる読み込み時にアドレス空間レイアウト randomization (ASLR) を使用して指定します。|
|[/ERRORREPORT](errorreport-editbin-exe.md)|内部エラーを Microsoft に報告します。|
|[/HEAP](heap.md)|実行可能イメージのヒープのサイズをバイト単位で設定します。|
|[/HIGHENTROPYVA](highentropyva.md)|DLL または実行可能イメージが高エントロピ (64 ビット) のアドレス空間レイアウト randomization (ASLR) をサポートしているかどうかを指定します。|
|[/INTEGRITYCHECK](integritycheck.md)|読み込み時にデジタル署名を確認するかどうかを指定します。|
|[/LARGEADDRESSAWARE](largeaddressaware.md)|オブジェクトには 2 ギガバイトを超えるアドレスがサポートするかどうかを指定します。|
|[/NOLOGO](nologo-editbin.md)|EDITBIN 著作権情報を表示しません。|
|[/NXCOMPAT](nxcompat.md)|実行可能イメージが Windows データ実行防止と互換性のあるかどうかを指定します。|
|[/REBASE](rebase.md)|指定したオブジェクトのベース アドレスを設定します。|
|[/RELEASE](release.md)|ヘッダーにチェックサムを設定します。|
|[/SECTION](section-editbin.md)|セクションの属性をオーバーライドします。|
|[/STACK](stack.md)|実行可能イメージのスタックのサイズをバイト単位で設定します。|
|[/SUBSYSTEM](subsystem.md)|実行環境を指定します。|
|[/SWAPRUN](swaprun.md)|実行可能イメージのスワップ ファイルにコピーし、し、そこから実行する必要がありますを指定します。|
|[/TSAWARE](tsaware.md)|アプリの目的は、マルチ ユーザー環境で実行することを指定します。|
|[/VERSION](version.md)|ヘッダーにバージョン番号を設定します。|

## <a name="see-also"></a>関連項目

[追加の MSVC ビルド ツール](c-cpp-build-tools.md)<br/>
[EDITBIN リファレンス](editbin-reference.md)
