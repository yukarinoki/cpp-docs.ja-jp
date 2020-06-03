---
title: CArchive オブジェクトを作成する 2 つの方法
ms.date: 11/04/2016
helpviewer_keywords:
- CArchive class [MFC], closing CArchive objects
- CArchive objects [MFC], closing
- I/O [MFC], creating CArchive objects
- serialization [MFC], CArchive class
- CArchive objects [MFC]
- storage [MFC], CArchive class [MFC]
- data storage [MFC], CArchive class
- CArchive class [MFC], constructor
ms.assetid: aefa28ce-b55c-40dc-9e42-5f038030985d
ms.openlocfilehash: 71592584d4ecdd3169ad894861a97fa668c04ee8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370958"
---
# <a name="two-ways-to-create-a-carchive-object"></a>CArchive オブジェクトを作成する 2 つの方法

オブジェクトを作成するには、次の`CArchive`2 つの方法があります。

- [フレームワークを介した CArchive オブジェクトの暗黙的な作成](#_core_implicit_creation_of_a_carchive_object_via_the_framework)

- [CArchive オブジェクトの明示的な作成](#_core_explicit_creation_of_a_carchive_object)

## <a name="implicit-creation-of-a-carchive-object-via-the-framework"></a><a name="_core_implicit_creation_of_a_carchive_object_via_the_framework"></a>フレームワークを介した CArchive オブジェクトの暗黙的な作成

最も一般的で最も簡単な方法は、[ファイル]`CArchive`メニューの [保存]、[名前を付けて保存]、および [開く] コマンドの代わりに、フレームワークがドキュメントのオブジェクトを作成することです。

アプリケーションのユーザーが [ファイル] メニューの [名前を付けて保存] コマンドを発行した場合のフレームワークの動作を次に示します。

1. [**名前を付けて保存**] ダイアログ ボックスを表示し、ユーザーからファイル名を取得します。

1. ユーザーがオブジェクトとして指定したファイルを`CFile`開きます。

1. この`CFile`オブジェクト`CArchive`を指すオブジェクトを作成します。 オブジェクトを作成`CArchive`する際、フレームワークはモードを"読み込み"(読み込み、逆シリアル化)ではなく、"ストア"(書き込み、シリアル化)に設定します。

1. 派生クラス`Serialize`で定義されている関数`CDocument`を呼び出し、オブジェクトへの参照を`CArchive`渡します。

ドキュメントの`Serialize`関数は、後で説明したように、`CArchive`オブジェクトにデータを書き込みます。 `Serialize`関数から戻ると、フレームワークはオブジェクトを`CArchive`破棄し、次にオブジェクト`CFile`を破棄します。

したがって、フレームワークにドキュメントのオブジェクトを`CArchive`作成させる場合、アーカイブとの間で書き込みと読み取`Serialize`りを行うドキュメントの関数を実装する必要があります。 また、ドキュメントの`Serialize``CObject``Serialize`関数が直接または間接的にシリアル化する派生オブジェクトについても実装する必要があります。

## <a name="explicit-creation-of-a-carchive-object"></a><a name="_core_explicit_creation_of_a_carchive_object"></a>CArchive オブジェクトの明示的な作成

フレームワークを介してドキュメントをシリアル化する以外に、`CArchive`オブジェクトが必要な場合もあります。 たとえば、オブジェクトによって表されるクリップボードとの間でデータをシリアル化する場合があります`CSharedFile`。 または、フレームワークによって提供されるファイルとは異なるファイルを保存するためにユーザー インターフェイスを使用することもできます。 この場合、`CArchive`オブジェクトを明示的に作成できます。 これは、フレームワークと同じ方法で、次の手順を使用して行います。

#### <a name="to-explicitly-create-a-carchive-object"></a>CArchive オブジェクトを明示的に作成するには

1. から`CFile`派生`CFile`したオブジェクトまたはオブジェクトを構築します。

1. オブジェクトを`CFile`のコンストラクターに渡`CArchive`します( の例を参照してください)。

   [!code-cpp[NVC_MFCSerialization#5](../mfc/codesnippet/cpp/two-ways-to-create-a-carchive-object_1.cpp)]

   コンストラクターの 2`CArchive`番目の引数は、ファイルへのデータの格納または読み込みにアーカイブを使用するかどうかを指定する列挙値です。 オブジェクト`Serialize`の関数は、アーカイブ オブジェクトの関数を`IsStoring`呼び出すことによって、この状態をチェックします。

オブジェクトへのデータの保存または読み込みが完了したら`CArchive`、オブジェクトを閉じます。 `CArchive` (および`CFile`) オブジェクトは自動的にアーカイブ (およびファイル) を閉じますが、エラーからの回復が容易になるので、明示的に閉じるのが良い方法です。 エラー処理の詳細については、「[例外: 例外のキャッチと削除](../mfc/exceptions-catching-and-deleting-exceptions.md)」を参照してください。

#### <a name="to-close-the-carchive-object"></a>CArchive オブジェクトを閉じるには

1. 次の例は、オブジェクトを閉じる`CArchive`方法を示しています。

   [!code-cpp[NVC_MFCSerialization#6](../mfc/codesnippet/cpp/two-ways-to-create-a-carchive-object_2.cpp)]

## <a name="see-also"></a>関連項目

[シリアル化 : オブジェクトのシリアル化](../mfc/serialization-serializing-an-object.md)
