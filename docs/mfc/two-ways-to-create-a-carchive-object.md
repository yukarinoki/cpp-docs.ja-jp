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
ms.openlocfilehash: 38642906b0973730149ed0de5381519f06d69fe5
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79442027"
---
# <a name="two-ways-to-create-a-carchive-object"></a>CArchive オブジェクトを作成する 2 つの方法

`CArchive` オブジェクトを作成するには、次の2つの方法があります。

- [フレームワークを使用した CArchive オブジェクトの暗黙的な作成](#_core_implicit_creation_of_a_carchive_object_via_the_framework)

- [CArchive オブジェクトの明示的な作成](#_core_explicit_creation_of_a_carchive_object)

##  <a name="_core_implicit_creation_of_a_carchive_object_via_the_framework"></a>フレームワークを使用した CArchive オブジェクトの暗黙的な作成

最も一般的で最も簡単な方法は、[ファイル] メニューの [保存]、[名前を付けて保存]、[名前を付けて保存] コマンドを使用して、フレームワークがドキュメントの `CArchive` オブジェクトを作成できるようにすることです。

ここでは、アプリケーションのユーザーが [ファイル] メニューから [名前を付けて保存] コマンドを発行した場合のフレームワークの動作を示します。

1. **[名前を付けて保存]** ダイアログボックスを表示し、ユーザーからファイル名を取得します。

1. ユーザーによって指定されたファイルを `CFile` オブジェクトとして開きます。

1. この `CFile` オブジェクトを指す `CArchive` オブジェクトを作成します。 `CArchive` オブジェクトを作成する場合、フレームワークは "読み込み" (読み取り、逆シリアル化) ではなく、"格納" (書き込み、シリアル化) にモードを設定します。

1. `CDocument`派生クラスで定義されている `Serialize` 関数を呼び出し、`CArchive` オブジェクトへの参照を渡します。

ドキュメントの `Serialize` 関数は、後で説明するように、`CArchive` オブジェクトにデータを書き込みます。 `Serialize` 関数から戻ると、フレームワークによって `CArchive` オブジェクトと `CFile` オブジェクトが破棄されます。

したがって、フレームワークでドキュメントの `CArchive` オブジェクトを作成する場合は、アーカイブとの間で読み書きを行うドキュメントの `Serialize` 関数を実装するだけで済みます。 また、ドキュメントの `Serialize` 関数が直接または間接的にシリアル化する `CObject`派生オブジェクトの `Serialize` も実装する必要があります。

##  <a name="_core_explicit_creation_of_a_carchive_object"></a>CArchive オブジェクトの明示的な作成

フレームワークを使用してドキュメントをシリアル化するだけでなく、`CArchive` オブジェクトが必要になる場合もあります。 たとえば、`CSharedFile` オブジェクトによって表されるクリップボードとの間でデータをシリアル化することができます。 または、フレームワークによって提供されるものとは異なるファイルを保存するために、ユーザーインターフェイスを使用することもできます。 この場合は、`CArchive` オブジェクトを明示的に作成できます。 これは、次の手順を使用して、フレームワークと同じ方法で行います。

#### <a name="to-explicitly-create-a-carchive-object"></a>CArchive オブジェクトを明示的に作成するには

1. `CFile`から派生した `CFile` オブジェクトまたはオブジェクトを構築します。

1. 次の例に示すように、`CFile` オブジェクトを `CArchive`のコンストラクターに渡します。

   [!code-cpp[NVC_MFCSerialization#5](../mfc/codesnippet/cpp/two-ways-to-create-a-carchive-object_1.cpp)]

   `CArchive` コンストラクターの2番目の引数は、ファイルへのデータの格納または読み込みにアーカイブを使用するかどうかを指定する列挙値です。 オブジェクトの `Serialize` 関数は、archive オブジェクトの `IsStoring` 関数を呼び出すことによって、この状態をチェックします。

`CArchive` オブジェクトとの間でのデータの保存または読み込みが完了したら、閉じます。 `CArchive` (および `CFile`) のオブジェクトはアーカイブ (およびファイル) を自動的に閉じますが、エラーからの回復を容易にするため、明示的に実行することをお勧めします。 エラー処理の詳細については、「[例外: 例外のキャッチと削除](../mfc/exceptions-catching-and-deleting-exceptions.md)」を参照してください。

#### <a name="to-close-the-carchive-object"></a>CArchive オブジェクトを閉じるには

1. 次の例は、`CArchive` オブジェクトを閉じる方法を示しています。

   [!code-cpp[NVC_MFCSerialization#6](../mfc/codesnippet/cpp/two-ways-to-create-a-carchive-object_2.cpp)]

## <a name="see-also"></a>参照

[シリアル化: オブジェクトのシリアル化](../mfc/serialization-serializing-an-object.md)
