---
description: '詳細について: テクニカルノート 2: 永続的なオブジェクトのデータ形式'
title: 'テクニカル ノート 2: 永続オブジェクトのデータ形式'
ms.date: 11/04/2016
helpviewer_keywords:
- VERSIONABLE_SCHEMA macro [MFC]
- persistent object data
- CArchive class [MFC], support for persistent data
- persistent C++ objects [MFC]
- TN002
ms.assetid: 553fe01d-c587-4c8d-a181-3244a15c2be9
ms.openlocfilehash: e99d54bd2624bffac4f5fea37c72bb7719e1e408
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216081"
---
# <a name="tn002-persistent-object-data-format"></a>テクニカル ノート 2: 永続オブジェクトのデータ形式

このメモでは、永続 C++ オブジェクトをサポートする MFC ルーチンと、ファイルに格納されるときのオブジェクトデータの形式について説明します。 これは、 [DECLARE_SERIAL](../mfc/reference/run-time-object-model-services.md#declare_serial) マクロおよび [IMPLEMENT_SERIAL](../mfc/reference/run-time-object-model-services.md#implement_serial) マクロを持つクラスにのみ適用されます。

## <a name="the-problem"></a>問題

永続データの MFC 実装では、ファイルの1つの隣接部分に多数のオブジェクトのデータが格納されます。 オブジェクトのメソッドは、 `Serialize` オブジェクトのデータをコンパクトなバイナリ形式に変換します。

の実装により、すべてのデータが確実に同じ形式で保存されます。 [CArchive クラス](../mfc/reference/carchive-class.md)を使用します。 オブジェクトは、 `CArchive` 翻訳者として使用されます。 このオブジェクトは、 [CArchive:: Close](../mfc/reference/carchive-class.md#close)を呼び出すまで作成された時点で保持されます。 このメソッドは、プログラマが明示的に呼び出すか、を含むスコープを終了するときにデストラクターによって暗黙的に呼び出すことができ `CArchive` ます。

このメモでは、 `CArchive` メンバー [CArchive:: ReadObject](../mfc/reference/carchive-class.md#readobject) と [carchive:: WriteObject](../mfc/reference/carchive-class.md#writeobject)の実装について説明します。 これらの関数のコードは、Arcobj .cpp に含まれています。また、Arccore のの主な実装でも見つかります。 `CArchive` ユーザーコードがとを直接呼び出すことはありません `ReadObject` `WriteObject` 。 代わりに、これらのオブジェクトは、DECLARE_SERIAL および IMPLEMENT_SERIAL マクロによって自動的に生成されるクラス固有の型セーフな挿入演算子と抽出演算子によって使用されます。 次のコードは、 `WriteObject` と `ReadObject` が暗黙的に呼び出される方法を示しています。

```
class CMyObject : public CObject
{
    DECLARE_SERIAL(CMyObject)
};

IMPLEMENT_SERIAL(CMyObj, CObject, 1)

// example usage (ar is a CArchive&)
CMyObject* pObj;
CArchive& ar;
ar <<pObj;        // calls ar.WriteObject(pObj)
ar>> pObj;        // calls ar.ReadObject(RUNTIME_CLASS(CObj))
```

## <a name="saving-objects-to-the-store-carchivewriteobject"></a>ストアにオブジェクトを保存しています (CArchive:: WriteObject)

メソッドは、 `CArchive::WriteObject` オブジェクトの再構築に使用されるヘッダーデータを書き込みます。 このデータは、オブジェクトの型とオブジェクトの状態の2つの部分で構成されます。 また、このメソッドは、書き込まれるオブジェクトの id を保持し、そのオブジェクトへのポインターの数 (循環ポインターを含む) に関係なく、1つのコピーのみが保存されるようにします。

オブジェクトの保存 (挿入) と復元 (抽出) は、複数の "マニフェスト定数" に依存します。 これらは、バイナリに格納され、アーカイブに重要な情報を提供する値です ("w" プレフィックスは16ビットの数量を示します)。

|タグ|説明|
|---------|-----------------|
|wNullTag|NULL オブジェクトポインター (0) に使用されます。|
|wNewClassTag|次に示すクラスの説明が、このアーカイブコンテキスト (-1) の新しいものであることを示します。|
|wOldClassTag|読み取り対象のオブジェクトのクラスが、このコンテキスト (0x8000) で認識されたことを示します。|

オブジェクトを格納する場合、アーカイブは [CMapPtrToPtr](../mfc/reference/cmapptrtoptr-class.md) ( *m_pStoreMap*) を保持します。これは、格納されているオブジェクトから32ビットの永続識別子 (PID) へのマッピングです。 PID は、すべての一意のオブジェクトと、アーカイブのコンテキストで保存されるすべての一意のクラス名に割り当てられます。 これらの Pid は、1から順番に渡されます。 これらの Pid はアーカイブの範囲外では意味を持ちません。特に、レコード番号やその他の id 項目と混同することはありません。

クラスで `CArchive` は、pid は32ビットですが、0x7FFE より大きい場合を除き、16ビットとして書き込まれます。 大きな Pid は、32ビットの PID を続けた大きさで書き込まれます。 これにより、以前のバージョンで作成されたプロジェクトとの互換性が維持されます。

オブジェクトをアーカイブに保存する要求 (通常はグローバル挿入演算子を使用) が行われると、NULL の [CObject](../mfc/reference/cobject-class.md) ポインターに対するチェックが行われます。 ポインターが NULL の場合、 *Wnulltag* がアーカイブストリームに挿入されます。

ポインターが NULL ではなく、シリアル化できる (クラスがクラスである) 場合、 `DECLARE_SERIAL` コードは *m_pStoreMap* をチェックして、オブジェクトが既に保存されているかどうかを確認します。 含まれている場合、コードはそのオブジェクトに関連付けられた32ビット PID をアーカイブストリームに挿入します。

オブジェクトが以前に保存されていない場合は、次の2つの考えられる可能性があります。オブジェクトのオブジェクトと正確な型 (つまり、クラス) がこのアーカイブコンテキストの新しいものであるか、またはオブジェクトが既に表示されている正確な型であること。 型が検出されたかどうかを判断するために、コード[](../mfc/reference/cruntimeclass-structure.md)は、保存されている `CRuntimeClass` オブジェクトに関連付けられているオブジェクトと一致する CRuntimeClass オブジェクトの m_pStoreMap をクエリします。 一致するものがある場合は、 `WriteObject` `OR` *wOldClassTag* とこのインデックスのビット単位のタグが挿入されます。 `CRuntimeClass`がこのアーカイブコンテキストの新しい場合は、に `WriteObject` よって新しい PID がそのクラスに割り当てられ、 *wNewClassTag* 値が前にアーカイブに挿入されます。

このクラスの記述子は、メソッドを使用してアーカイブに挿入され `CRuntimeClass::Store` ます。 `CRuntimeClass::Store` クラスのスキーマ番号 (下記参照) と、クラスの ASCII テキスト名を挿入します。 ASCII テキスト名を使用しても、アプリケーション間でのアーカイブの一意性は保証されないことに注意してください。 そのため、破損を防ぐためにデータファイルにタグを付ける必要があります。 クラス情報を挿入した後、アーカイブはオブジェクトを *m_pStoreMap* に格納し、メソッドを呼び出して `Serialize` クラス固有のデータを挿入します。 を呼び出す前にオブジェクトを *m_pStoreMap* に配置すると `Serialize` 、オブジェクトの複数のコピーがストアに保存されなくなります。

最初の呼び出し元 (通常はオブジェクトのネットワークのルート) に戻るときに、 [CArchive:: Close](../mfc/reference/carchive-class.md#close)を呼び出す必要があります。 他の [CFile](../mfc/reference/cfile-class.md)操作を実行する場合は、 `CArchive` アーカイブが破損しないように、メソッドの [フラッシュ](../mfc/reference/carchive-class.md#flush) を呼び出す必要があります。

> [!NOTE]
> この実装は、アーカイブコンテキストごとに0x3FFFFFFE インデックスのハード制限を設けています。 この数は、1つのアーカイブに保存できる一意のオブジェクトとクラスの最大数を表しますが、1つのディスクファイルに格納できるアーカイブコンテキストの数に制限はありません。

## <a name="loading-objects-from-the-store-carchivereadobject"></a>ストアからのオブジェクトの読み込み (CArchive:: ReadObject)

オブジェクトの読み込み (抽出) は、メソッドを使用 `CArchive::ReadObject` し、と逆に `WriteObject` なります。 と同様に `WriteObject` 、 `ReadObject` はユーザーコードによって直接呼び出されるわけではありません。ユーザーコードは、予期されるを使用してを呼び出すタイプセーフな抽出演算子を呼び出す必要があり `ReadObject` `CRuntimeClass` ます。 これにより、抽出操作の型の整合性が保証されます。

1から `WriteObject` 始まる (0 は NULL オブジェクトとして事前定義されています) ので、この実装では、より高い pid が割り当てられています。そのため、実装では、配列を使用して `ReadObject` アーカイブコンテキストの状態を維持できます。 Pid がストアから読み取られるときに、PID が *m_pLoadArray* の現在の上限を超えている場合、は `ReadObject` 新しいオブジェクト (またはクラスの説明) が続いていることを認識します。

## <a name="schema-numbers"></a>スキーマ番号

クラスのメソッドが検出されたときにクラスに割り当てられるスキーマ番号 `IMPLEMENT_SERIAL` は、クラス実装の "バージョン" です。 スキーマは、特定のオブジェクトが永続化された回数 (通常はオブジェクトバージョンと呼ばれます) ではなく、クラスの実装を参照します。

同じクラスの複数の実装を時間の経過と共に維持する場合、オブジェクトのメソッド実装を変更するときにスキーマを増やすと、 `Serialize` 以前のバージョンの実装を使用して格納されたオブジェクトを読み込むことができるコードを記述できるようになります。

メソッドは、 `CArchive::ReadObject` メモリ内のクラスの説明とは異なるスキーマ番号を永続ストアで検出すると、 [Cアーカイブ例外](../mfc/reference/carchiveexception-class.md) をスローします。 この例外から回復するのは簡単ではありません。

`VERSIONABLE_SCHEMA`スキーマバージョンと組み合わせてを使用して、この例外がスローされないようにすることができます。 を使用することにより `VERSIONABLE_SCHEMA` 、コードは、 `Serialize` [CArchive:: getobjectschema](../mfc/reference/carchive-class.md#getobjectschema)から戻り値をチェックすることによって、関数内で適切なアクションを実行できます。

## <a name="calling-serialize-directly"></a>シリアル化を直接呼び出す

多くの場合、との一般的なオブジェクトアーカイブスキームの `WriteObject` オーバーヘッド `ReadObject` は必要ありません。 これは、データを [CDocument](../mfc/reference/cdocument-class.md)にシリアル化する場合の一般的なケースです。 この場合、 `Serialize` のメソッドは、 `CDocument` extract または insert 演算子ではなく、直接呼び出されます。 ドキュメントの内容によって、より一般的なオブジェクトアーカイブスキームが使用される場合があります。

`Serialize`直接を呼び出すと、次のような長所と短所があります。

- オブジェクトをシリアル化する前または後に、追加のバイトがアーカイブに追加されることはありません。 これにより、保存されたデータが小さくなるだけでなく、 `Serialize` 任意のファイル形式を処理できるルーチンを実装できるようになります。

- MFC はチューニングされているため、 `WriteObject` および `ReadObject` の実装と関連するコレクションは、他の目的でより一般的なオブジェクトアーカイブスキームが必要な場合を除き、アプリケーションにリンクされません。

- コードは、古いスキーマ番号から復旧する必要はありません。 これにより、スキーマ番号、ファイル形式のバージョン番号、またはデータファイルの開始時に使用する番号を識別するドキュメントのシリアル化コードが作成されます。

- を直接呼び出してシリアル化されたオブジェクトは、を `Serialize` 使用し `CArchive::GetObjectSchema` たり、(UINT) の戻り値を処理したりする必要があります。この場合、バージョンが不明であることを示します。

`Serialize`はドキュメントに直接呼び出されるので、通常、ドキュメントのサブオブジェクトが親ドキュメントへの参照をアーカイブすることはできません。 これらのオブジェクトには、コンテナードキュメントへの明示的なポインターを与えるか、または、これらのバックポインターをアーカイブする前に、 [CArchive:: MapObject](../mfc/reference/carchive-class.md#mapobject) 関数を使用してポインターを PID にマップする必要があり `CDocument` ます。

既に説明したように、を直接呼び出すときは、バージョン情報とクラス情報を自分でエンコードする必要があり `Serialize` ます。これにより、古いファイルとの下位互換性を維持したまま、後で形式を変更できます。 関数は、 `CArchive::SerializeClass` オブジェクトを直接シリアル化する前に、または基底クラスを呼び出す前に明示的に呼び出すことができます。

## <a name="see-also"></a>関連項目

[番号別テクニカルノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカルノート](../mfc/technical-notes-by-category.md)
