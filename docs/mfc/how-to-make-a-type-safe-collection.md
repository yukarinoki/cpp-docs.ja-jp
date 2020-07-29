---
title: '方法 : タイプ セーフなコレクションを作成する'
ms.date: 11/04/2016
helpviewer_keywords:
- type-safe collections [MFC]
- serializing collection-class elements [MFC]
- collection classes [MFC], type safety
- SerializeElements function [MFC]
- collection classes [MFC], template-based
- serialization [MFC], collection classes
- collection classes [MFC], deriving from nontemplate
ms.assetid: 7230b2db-4283-4083-b098-eb231bf5b89e
ms.openlocfilehash: 7e6b0a4181607feaf6e92f5d92d95cb055761aa4
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228623"
---
# <a name="how-to-make-a-type-safe-collection"></a>方法 : タイプ セーフなコレクションを作成する

この記事では、独自のデータ型に対してタイプセーフなコレクションを作成する方法について説明します。 取り上げるトピックは次のとおりです。

- [タイプセーフでのテンプレートベースのクラスの使用](#_core_using_template.2d.based_classes_for_type_safety)

- [ヘルパー関数の実装](#_core_implementing_helper_functions)

- [非テンプレートコレクションクラスの使用](#_core_using_nontemplate_collection_classes)

Microsoft Foundation Class ライブラリには、C++ テンプレートに基づく定義済みのタイプセーフなコレクションが用意されています。 これらのクラスはテンプレートなので、型キャストや、非テンプレートクラスを使用するために必要なその他の追加作業を行わずに、タイプセーフで使いやすさを提供するのに役立ちます。 MFC サンプル[収集](../overview/visual-cpp-samples.md)は、mfc アプリケーションでテンプレートベースのコレクションクラスを使用する方法を示しています。 一般に、新しいコレクションコードを記述するときは常にこれらのクラスを使用します。

## <a name="using-template-based-classes-for-type-safety"></a><a name="_core_using_template.2d.based_classes_for_type_safety"></a>タイプセーフでのテンプレートベースのクラスの使用

#### <a name="to-use-template-based-classes"></a>テンプレートベースのクラスを使用するには

1. コレクションクラス型の変数を宣言します。 次に例を示します。

   [!code-cpp[NVC_MFCCollections#7](codesnippet/cpp/how-to-make-a-type-safe-collection_1.cpp)]

1. コレクションオブジェクトのメンバー関数を呼び出します。 次に例を示します。

   [!code-cpp[NVC_MFCCollections#8](codesnippet/cpp/how-to-make-a-type-safe-collection_2.cpp)]

1. 必要に応じて、[ヘルパー関数](reference/collection-class-helpers.md)と[SerializeElements](reference/collection-class-helpers.md#serializeelements)を実装します。 これらの関数の実装の詳細については、「[ヘルパー関数の実装](#_core_implementing_helper_functions)」を参照してください。

この例では、整数のリストの宣言を示します。 手順 1. の最初のパラメーターは、リストの要素として格納されるデータの種類です。 2番目のパラメーターは、コレクションクラスのメンバー関数 (やなど) との間でデータをやり取りする方法を指定し `Add` `GetAt` ます。

## <a name="implementing-helper-functions"></a><a name="_core_implementing_helper_functions"></a>ヘルパー関数の実装

テンプレートベースのコレクションクラス、 `CArray` `CList` 、およびは、 `CMap` 5 つのグローバルヘルパー関数を使用します。これは、派生コレクションクラスに必要に応じてカスタマイズできます。 これらのヘルパー関数の詳細については、「 *MFC リファレンス*」の「[コレクションクラスヘルパー](reference/collection-class-helpers.md) 」を参照してください。 テンプレートベースのコレクションクラスのほとんどの使用には、シリアル化関数の実装が必要です。

### <a name="serializing-elements"></a><a name="_core_serializing_elements"></a>シリアル化 (要素を)

、、およびの各クラスは、を呼び出して、 `CArray` `CList` `CMap` `SerializeElements` コレクションの要素をアーカイブに格納するか、アーカイブから読み取ります。

ヘルパー関数の既定の実装では、オブジェクト `SerializeElements` からアーカイブへのビットごとの書き込み、またはオブジェクトがアーカイブに格納されているかどうかに応じて、アーカイブからオブジェクトへのビットごとの読み取りを行います。 `SerializeElements`このアクションが適切でない場合は、をオーバーライドします。

コレクションがから派生したオブジェクト `CObject` を格納し、その `IMPLEMENT_SERIAL` マクロを collection 要素クラスの実装で使用する場合は、とに組み込まれているシリアル化機能を利用でき `CArchive` `CObject` ます。

[!code-cpp[NVC_MFCCollections#9](codesnippet/cpp/how-to-make-a-type-safe-collection_3.cpp)]

`CArchive` `CObject::Serialize` 各オブジェクトの呼び出し (またはその関数のオーバーライド) のオーバーロードされた挿入演算子 `CPerson` 。

## <a name="using-nontemplate-collection-classes"></a><a name="_core_using_nontemplate_collection_classes"></a>非テンプレートコレクションクラスの使用

MFC では、MFC バージョン1.0 で導入されたコレクションクラスもサポートされています。 これらのクラスは、テンプレートに基づいていません。 サポートされている型、、、およびのデータを格納するために使用でき `CObject*` `UINT` `DWORD` `CString` ます。 これらの定義済みコレクション (など) を使用して `CObList` 、から派生したオブジェクトのコレクションを保持でき `CObject` ます。 MFC には `UINT` 、や void ポインター () などのプリミティブ型を保持するための、他の定義済みコレクションも用意されて **`void*`** います。 ただし、一般的には、より具体的なクラスとその派生クラスのオブジェクトを保持するために、独自のタイプセーフなコレクションを定義すると便利です。 テンプレートに基づいていないコレクションクラスを使用する場合は、テンプレートベースのクラスを使用するよりも作業が多くなります。

非テンプレートコレクションでタイプセーフなコレクションを作成するには、次の2つの方法があります。

1. 必要に応じて型キャストを使用して、非テンプレートコレクションを使用します。 これは簡単な方法です。

1. から派生し、非テンプレートタイプセーフなコレクションを拡張します。

#### <a name="to-use-the-nontemplate-collections-with-type-casting"></a>非テンプレートコレクションを型キャストで使用するには

1. などの非テンプレートクラスの1つを `CWordArray` 直接使用します。

   たとえば、を作成 `CWordArray` し、32ビット値を追加してから取得することができます。 これ以上の操作はありません。 定義済みの機能を使用するだけです。

   また、定義済みのコレクション (など) を使用して `CObList` 、から派生したオブジェクトを保持することもでき `CObject` ます。 `CObList`コレクションは、へのポインターを保持するために定義され `CObject` ます。 リストからオブジェクトを取得する場合、関数がへのポインターを返すため、結果を適切な型にキャストすることが必要になる場合があり `CObList` `CObject` ます。 たとえば、オブジェクトをコレクションに格納する場合は、取得した `CPerson` `CObList` 要素をオブジェクトへのポインターにキャストする必要があり `CPerson` ます。 次の例では、コレクションを使用して `CObList` オブジェクトを保持し `CPerson` ます。

   [!code-cpp[NVC_MFCCollections#10](codesnippet/cpp/how-to-make-a-type-safe-collection_4.cpp)]

   このように定義済みのコレクション型を使用し、必要に応じてキャストする方法は、コレクションのニーズの多くに適している場合があります。 さらに機能またはタイプセーフが必要な場合は、テンプレートベースのクラスを使用するか、次の手順に従います。

#### <a name="to-derive-and-extend-a-nontemplate-type-safe-collection"></a>非テンプレートタイプセーフコレクションを派生して拡張するには

1. 定義済みの非テンプレートクラスの1つから独自のコレクションクラスを派生させます。

   クラスを派生させると、タイプセーフなラッパー関数を追加して、既存の関数にタイプセーフなインターフェイスを提供できます。

   たとえば、オブジェクトを保持するためにからリストを派生させる場合は、 `CObList` `CPerson` `AddHeadPerson` 次に示すように、ラッパー関数とを追加することができ `GetHeadPerson` ます。

   [!code-cpp[NVC_MFCCollections#11](codesnippet/cpp/how-to-make-a-type-safe-collection_5.h)]

   これらのラッパー関数は、派生リストからオブジェクトを追加および取得するためのタイプセーフな方法を提供し `CPerson` ます。 関数の場合は、単純に型キャストをカプセル化するだけであることがわかり `GetHeadPerson` ます。

   また、既存の機能をタイプセーフラッパーにラップするだけではなく、コレクションの機能を拡張する新しい関数を定義して、新しい機能を追加することもできます。 たとえば、 [CObject コレクション内のすべてのオブジェクトを削除](deleting-all-objects-in-a-cobject-collection.md)する記事では、一覧に含まれるすべてのオブジェクトを削除する関数について説明しています。 この関数は、メンバー関数として派生クラスに追加できます。

## <a name="see-also"></a>関連項目

[コレクション](collections.md)
