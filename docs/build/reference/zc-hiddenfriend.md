---
title: '/Zc: hiddenFriend (標準 C++ の非表示フレンド規則を適用する)'
description: '準拠または緩和されたフレンド互換性のための Microsoft C++/Zc: hiddenFriend コンパイラオプションについて説明します。'
ms.date: 01/23/2021
f1_keywords:
- /Zc:hiddenFriend
helpviewer_keywords:
- /Zc:hiddenFriend
- Zc:hiddenFriend
- -Zc:hiddenFriend
ms.openlocfilehash: 5a3487cc4899cf6a07e91dc5ce5b7cd8f8784737
ms.sourcegitcommit: 74e58bee5cffb30b66e17be6dbfde2544369638e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2021
ms.locfileid: "98766867"
---
# <a name="zchiddenfriend-enforce-standard-c-hidden-friend-rules"></a>`/Zc:hiddenFriend` (標準 C++ の非表示フレンド規則を適用します)

コンパイラが、隠ぺいされたフレンド関数または関数テンプレートの C++ 標準処理に準拠していることを指定します。

## <a name="syntax"></a>構文

> **`/Zc:hiddenFriend`**\[**`-`**]

## <a name="remarks"></a>解説

オプションを指定すると、 **`/Zc:hiddenFriend`** オプションの動作のサブセットが有効になり [`/permissive-`](permissive-standards-conformance.md) ます。 これは、非表示のフレンドの標準に準拠するようにコンパイラに指示します。 コンパイラには、明示的なインスタンスの場合は [引数依存の参照](../../cpp/argument-dependent-name-koenig-lookup-on-functions.md) (ADL)、外側のクラス型のテンプレートパラメーターには非表示のフレンドのみが含まれます。 この制限により、非表示のフレンドを使用して、型の操作を暗黙的な変換に適用できないようにすることができます。 このオプションを使用すると、他の方法では使用できないコードのビルド速度を向上させることができ [`/permissive-`](permissive-standards-conformance.md) ます。

*非表示のフレンド* は、 **`friend`** クラスまたはクラステンプレート定義内でのみ宣言された関数または関数テンプレートです。 既定では、Microsoft C++ コンパイラは、必要な場所にあるオーバーロードの解決の候補として、非表示のフレンド宣言を削除しません。 この従来の動作では、隠ぺいされたフレンド関数をより多くのコンテキストで候補として含めることにより、コンパイラが遅くなる可能性があります。

標準 C++ の非表示のフレンド動作は、では既定で有効になって **`/permissive-`** います。 オプションを指定したときに、従来の非表示のフレンド動作を指定するには **`/permissive-`** 、を使用 **`/Zc:hiddenFriend-`** します。 C++ 20 のモジュールを使用するには、標準の非表示フレンド動作が必要です。

この **`/Zc:hiddenFriend`** オプションは、Visual Studio 2019 バージョン16.4 以降で使用できます。

を指定するときのコンパイラの動作の例につい **`/Zc:hiddenFriend`** ては、「 [非表示のフレンド名の検索規則](./permissive-standards-conformance.md#hidden-friend-name-lookup-rules)」を参照してください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **コマンドライン**] プロパティページを選択します。

1. またはを含むように " **追加オプション** " プロパティを変更し、[ *`/Zc:hiddenFriend`* *`/Zc:hiddenFriend-`* **OK]** をクリックします。

## <a name="see-also"></a>関連項目

[`/Zc` 互換性](zc-conformance.md)\
[`/permissive-`](permissive-standards-conformance.md)
