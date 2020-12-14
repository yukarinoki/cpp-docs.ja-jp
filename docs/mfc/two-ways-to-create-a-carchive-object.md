---
description: 詳細については、次を参照してください。 CArchive オブジェクトを作成する2つの方法
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
ms.openlocfilehash: 21a4321eef2d93cf0b37d157f57e12fa1ba940c8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263856"
---
# <a name="two-ways-to-create-a-carchive-object"></a>CArchive オブジェクトを作成する 2 つの方法

オブジェクトを作成するには、次の2つの方法があり `CArchive` ます。

- [フレームワークを使用した CArchive オブジェクトの暗黙的な作成](#_core_implicit_creation_of_a_carchive_object_via_the_framework)

- [CArchive オブジェクトの明示的な作成](#_core_explicit_creation_of_a_carchive_object)

## <a name="implicit-creation-of-a-carchive-object-via-the-framework"></a><a name="_core_implicit_creation_of_a_carchive_object_via_the_framework"></a> フレームワークを使用した CArchive オブジェクトの暗黙的な作成

最も一般的で最も簡単な方法は、[ `CArchive` ファイル] メニューの [保存]、[名前を付けて保存]、[開く] コマンドの代わりに、フレームワークがドキュメントのオブジェクトを作成できるようにすることです。

ここでは、アプリケーションのユーザーが [ファイル] メニューから [名前を付けて保存] コマンドを発行した場合のフレームワークの動作を示します。

1. [ **名前を付けて保存** ] ダイアログボックスを表示し、ユーザーからファイル名を取得します。

1. ユーザーによって指定されたファイルをオブジェクトとして開き `CFile` ます。

1. `CArchive`このオブジェクトを指すオブジェクトを作成し `CFile` ます。 オブジェクトの作成時に、 `CArchive` フレームワークは、"読み込み" (読み取り、逆シリアル化) ではなく "格納" (書き込み、シリアル化) にモードを設定します。

1. `Serialize`派生クラスで定義されている関数を呼び出し `CDocument` 、オブジェクトへの参照を渡し `CArchive` ます。

ドキュメントの `Serialize` 関数は、後で説明するように、オブジェクトにデータを書き込み `CArchive` ます。 関数から戻る `Serialize` と、フレームワークによってオブジェクトとオブジェクトが破棄され `CArchive` `CFile` ます。

したがって、フレームワークがドキュメントのオブジェクトを作成できるようにする場合は、アーカイブとの間で読み書きを `CArchive` 行うドキュメントの関数を実装するだけで済み `Serialize` ます。 また `Serialize` `CObject` 、ドキュメントの `Serialize` 関数が直接または間接的にシリアル化する、派生オブジェクトに対しても実装する必要があります。

## <a name="explicit-creation-of-a-carchive-object"></a><a name="_core_explicit_creation_of_a_carchive_object"></a> CArchive オブジェクトの明示的な作成

フレームワークを使用してドキュメントをシリアル化するだけでなく、オブジェクトが必要になる場合もあり `CArchive` ます。 たとえば、オブジェクトによって表されるクリップボードとの間でデータをシリアル化することができ `CSharedFile` ます。 または、フレームワークによって提供されるものとは異なるファイルを保存するために、ユーザーインターフェイスを使用することもできます。 この場合は、明示的にオブジェクトを作成でき `CArchive` ます。 これは、次の手順を使用して、フレームワークと同じ方法で行います。

#### <a name="to-explicitly-create-a-carchive-object"></a>CArchive オブジェクトを明示的に作成するには

1. `CFile`オブジェクトまたはから派生したオブジェクトを構築 `CFile` します。

1. 次の `CFile` 例に示すように、オブジェクトをのコンストラクターに渡し `CArchive` ます。

   [!code-cpp[NVC_MFCSerialization#5](../mfc/codesnippet/cpp/two-ways-to-create-a-carchive-object_1.cpp)]

   コンストラクターの2番目の引数 `CArchive` は、ファイルへのデータの格納または読み込みにアーカイブを使用するかどうかを指定する列挙値です。 `Serialize`オブジェクトの関数は、archive オブジェクトの関数を呼び出すことによって、この状態をチェックし `IsStoring` ます。

オブジェクトとの間でのデータの保存または読み込みが完了 `CArchive` したら、閉じます。 `CArchive`(および `CFile` ) オブジェクトによってアーカイブ (およびファイル) が自動的に閉じられますが、エラーからの回復が簡単になるため、明示的に実行することをお勧めします。 エラー処理の詳細については、「 [例外: 例外のキャッチと削除](../mfc/exceptions-catching-and-deleting-exceptions.md)」を参照してください。

#### <a name="to-close-the-carchive-object"></a>CArchive オブジェクトを閉じるには

1. オブジェクトを閉じる方法を次の例に示し `CArchive` ます。

   [!code-cpp[NVC_MFCSerialization#6](../mfc/codesnippet/cpp/two-ways-to-create-a-carchive-object_2.cpp)]

## <a name="see-also"></a>関連項目

[シリアル化: オブジェクトのシリアル化](../mfc/serialization-serializing-an-object.md)
