---
title: 'テクニカル ノート 2: 永続オブジェクトのデータ形式'
ms.date: 11/04/2016
helpviewer_keywords:
- VERSIONABLE_SCHEMA macro [MFC]
- persistent object data
- CArchive class [MFC], support for persistent data
- persistent C++ objects [MFC]
- TN002
ms.assetid: 553fe01d-c587-4c8d-a181-3244a15c2be9
ms.openlocfilehash: 1880d5d43055966dea8ab16dc4f26bd4e4602ec5
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447129"
---
# <a name="tn002-persistent-object-data-format"></a>テクニカル ノート 2: 永続オブジェクトのデータ形式

このメモでは、永続C++オブジェクトをサポートする MFC ルーチンと、ファイルに格納されるときのオブジェクトデータの形式について説明します。 これは、 [DECLARE_SERIAL](../mfc/reference/run-time-object-model-services.md#declare_serial)マクロおよび[IMPLEMENT_SERIAL](../mfc/reference/run-time-object-model-services.md#implement_serial)マクロを持つクラスにのみ適用されます。

## <a name="the-problem"></a>問題

永続データの MFC 実装では、ファイルの1つの隣接部分に多数のオブジェクトのデータが格納されます。 オブジェクトの `Serialize` メソッドは、オブジェクトのデータをコンパクトなバイナリ形式に変換します。

の実装により、すべてのデータが確実に同じ形式で保存されます。 [CArchive クラス](../mfc/reference/carchive-class.md)を使用します。 トランスレーターとして `CArchive` オブジェクトを使用します。 このオブジェクトは、 [CArchive:: Close](../mfc/reference/carchive-class.md#close)を呼び出すまで作成された時点で保持されます。 このメソッドは、プログラマが明示的に呼び出すことも、プログラムが `CArchive`を含むスコープを終了したときにデストラクターによって暗黙的に呼び出すこともできます。

このメモでは、`CArchive` members [carchive:: ReadObject](../mfc/reference/carchive-class.md#readobject)と[Carchive:: WriteObject](../mfc/reference/carchive-class.md#writeobject)の実装について説明します。 これらの関数のコードは、Arcobj .cpp に含まれています。また、Arccore の `CArchive` の主要な実装もあります。 ユーザーコードは `ReadObject` を呼び出さず、直接 `WriteObject` します。 代わりに、これらのオブジェクトは、DECLARE_SERIAL および IMPLEMENT_SERIAL マクロによって自動的に生成されるクラス固有の型セーフな挿入演算子と抽出演算子によって使用されます。 次のコードは、`WriteObject` と `ReadObject` が暗黙的に呼び出される方法を示しています。

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

メソッド `CArchive::WriteObject` は、オブジェクトの再構築に使用されるヘッダーデータを書き込みます。 このデータは、オブジェクトの型とオブジェクトの状態の2つの部分で構成されます。 また、このメソッドは、書き込まれるオブジェクトの id を保持し、そのオブジェクトへのポインターの数 (循環ポインターを含む) に関係なく、1つのコピーのみが保存されるようにします。

オブジェクトの保存 (挿入) と復元 (抽出) は、複数の "マニフェスト定数" に依存します。 これらは、バイナリに格納され、アーカイブに重要な情報を提供する値です ("w" プレフィックスは16ビットの数量を示します)。

|タグ|説明|
|---------|-----------------|
|wNullTag|NULL オブジェクトポインター (0) に使用されます。|
|wNewClassTag|次に示すクラスの説明が、このアーカイブコンテキスト (-1) の新しいものであることを示します。|
|wOldClassTag|読み取り対象のオブジェクトのクラスが、このコンテキスト (0x8000) で認識されたことを示します。|

オブジェクトを格納する場合、アーカイブは[CMapPtrToPtr](../mfc/reference/cmapptrtoptr-class.md) ( *m_pStoreMap*) を保持します。これは、格納されているオブジェクトから32ビットの永続識別子 (PID) へのマッピングです。 PID は、すべての一意のオブジェクトと、アーカイブのコンテキストで保存されるすべての一意のクラス名に割り当てられます。 これらの Pid は、1から順番に渡されます。 これらの Pid はアーカイブの範囲外では意味を持ちません。特に、レコード番号やその他の id 項目と混同することはありません。

`CArchive` クラスでは、Pid は32ビットですが、0x7FFE より大きい場合を除き、16ビットとして書き込まれます。 大きな Pid は、32ビットの PID を続けた大きさで書き込まれます。 これにより、以前のバージョンで作成されたプロジェクトとの互換性が維持されます。

オブジェクトをアーカイブに保存する要求 (通常はグローバル挿入演算子を使用) が行われると、NULL の[CObject](../mfc/reference/cobject-class.md)ポインターに対するチェックが行われます。 ポインターが NULL の場合、 *Wnulltag*がアーカイブストリームに挿入されます。

ポインターが NULL ではなく、シリアル化できる (クラスが `DECLARE_SERIAL` クラスである) 場合、コードは*m_pStoreMap*を確認して、オブジェクトが既に保存されているかどうかを確認します。 含まれている場合、コードはそのオブジェクトに関連付けられた32ビット PID をアーカイブストリームに挿入します。

オブジェクトが以前に保存されていない場合は、次の2つの考えられる可能性があります。オブジェクトのオブジェクトと正確な型 (つまり、クラス) がこのアーカイブコンテキストの新しいものであるか、またはオブジェクトが既に表示されている正確な型であること。 型が検出されたかどうかを判断するために、コードは、保存されているオブジェクトに関連付けられた `CRuntimeClass` オブジェクトと一致する[CRuntimeClass](../mfc/reference/cruntimeclass-structure.md)オブジェクトの*m_pStoreMap*をクエリします。 一致するものがある場合、`WriteObject` は*wOldClassTag*とこのインデックスのビットごとの `OR` であるタグを挿入します。 `CRuntimeClass` がこのアーカイブコンテキストの新しいものである場合、`WriteObject` によってそのクラスに新しい PID が割り当てられ、 *wNewClassTag*値が前にアーカイブに挿入されます。

このクラスの記述子は、`CRuntimeClass::Store` メソッドを使用してアーカイブに挿入されます。 `CRuntimeClass::Store` クラスのスキーマ番号 (下記参照) と、クラスの ASCII テキスト名を挿入します。 ASCII テキスト名を使用しても、アプリケーション間でのアーカイブの一意性は保証されないことに注意してください。 そのため、破損を防ぐためにデータファイルにタグを付ける必要があります。 クラス情報が挿入されると、アーカイブによってオブジェクトが*m_pStoreMap*に格納され、`Serialize` メソッドを呼び出してクラス固有のデータが挿入されます。 `Serialize` を呼び出す前にオブジェクトを*m_pStoreMap*に配置すると、オブジェクトの複数のコピーがストアに保存されなくなります。

最初の呼び出し元 (通常はオブジェクトのネットワークのルート) に戻るときに、 [CArchive:: Close](../mfc/reference/carchive-class.md#close)を呼び出す必要があります。 他の[CFile](../mfc/reference/cfile-class.md)操作を実行する場合は、アーカイブの破損を防ぐために `CArchive` メソッドの[フラッシュ](../mfc/reference/carchive-class.md#flush)を呼び出す必要があります。

> [!NOTE]
>  この実装は、アーカイブコンテキストごとに0x3FFFFFFE インデックスのハード制限を設けています。 この数は、1つのアーカイブに保存できる一意のオブジェクトとクラスの最大数を表しますが、1つのディスクファイルに格納できるアーカイブコンテキストの数に制限はありません。

## <a name="loading-objects-from-the-store-carchivereadobject"></a>ストアからのオブジェクトの読み込み (CArchive:: ReadObject)

オブジェクトの読み込み (抽出) は、`CArchive::ReadObject` メソッドを使用し、`WriteObject`の逆になります。 `WriteObject`と同様に、`ReadObject` はユーザーコードによって直接呼び出されるわけではありません。ユーザーコードは、予期される `CRuntimeClass`で `ReadObject` を呼び出すタイプセーフな抽出演算子を呼び出す必要があります。 これにより、抽出操作の型の整合性が保証されます。

`WriteObject` の実装には、1 (NULL オブジェクトとして事前に定義されています) を先頭に付けて、Pid を増やしています。そのため、`ReadObject` の実装では、配列を使用してアーカイブコンテキストの状態を維持できます。 Pid がストアから読み取られるときに、PID が*m_pLoadArray*の現在の上限を超えると、`ReadObject` は新しいオブジェクト (またはクラスの説明) が続くことを認識します。

## <a name="schema-numbers"></a>スキーマ番号

クラスの `IMPLEMENT_SERIAL` メソッドが検出されたときにクラスに割り当てられるスキーマ番号は、クラス実装の "バージョン" です。 スキーマは、特定のオブジェクトが永続化された回数 (通常はオブジェクトバージョンと呼ばれます) ではなく、クラスの実装を参照します。

同じクラスの複数の異なる実装を時間の経過と共に維持する場合は、オブジェクトの `Serialize` メソッドの実装を変更するときにスキーマを増やすことで、古いバージョンの実装を使用して格納されたオブジェクトを読み込むことができるコードを記述できます。

`CArchive::ReadObject` メソッドは、メモリ内のクラスの説明とは異なるスキーマ番号を永続ストアで検出すると、 [Cアーカイブ例外](../mfc/reference/carchiveexception-class.md)をスローします。 この例外から回復するのは簡単ではありません。

この例外がスローされないようにするには、`VERSIONABLE_SCHEMA` を (ビットごと**の or**) スキーマバージョンと組み合わせて使用できます。 `VERSIONABLE_SCHEMA`を使用することにより、コードは、 [CArchive:: GetObjectSchema](../mfc/reference/carchive-class.md#getobjectschema)から戻り値をチェックすることによって、`Serialize` 関数で適切なアクションを実行できます。

## <a name="calling-serialize-directly"></a>シリアル化を直接呼び出す

多くの場合、`WriteObject` と `ReadObject` の一般的なオブジェクトアーカイブスキームのオーバーヘッドは必要ありません。 これは、データを[CDocument](../mfc/reference/cdocument-class.md)にシリアル化する場合の一般的なケースです。 この場合、`CDocument` の `Serialize` メソッドは、extract または insert 演算子ではなく、直接呼び出されます。 ドキュメントの内容によって、より一般的なオブジェクトアーカイブスキームが使用される場合があります。

`Serialize` を直接呼び出すには、次のような長所と短所があります。

- オブジェクトをシリアル化する前または後に、追加のバイトがアーカイブに追加されることはありません。 これにより、保存されたデータが小さくなるだけでなく、任意のファイル形式を処理できる `Serialize` ルーチンを実装できるようになります。

- MFC は、`WriteObject` および `ReadObject` の実装と関連コレクションが、他の目的でより一般的なオブジェクトアーカイブスキームを必要としない限り、アプリケーションにリンクされないようにチューニングされています。

- コードは、古いスキーマ番号から復旧する必要はありません。 これにより、スキーマ番号、ファイル形式のバージョン番号、またはデータファイルの開始時に使用する番号を識別するドキュメントのシリアル化コードが作成されます。

- `Serialize` の直接呼び出しを使用してシリアル化されるオブジェクトでは、`CArchive::GetObjectSchema` を使用したり、バージョンが不明であることを示す戻り値 (UINT)-1 を処理したりすることはできません。

`Serialize` はドキュメントで直接呼び出されるので、通常、ドキュメントのサブオブジェクトが親ドキュメントへの参照をアーカイブすることはできません。 これらのオブジェクトには、コンテナードキュメントへのポインターを明示的に指定するか、または[CArchive:: MapObject](../mfc/reference/carchive-class.md#mapobject)関数を使用して、これらのバックポインターをアーカイブする前に `CDocument` ポインターを PID にマップする必要があります。

前に説明したように、`Serialize` を直接呼び出すときは、バージョン情報とクラス情報を自分でエンコードして、後で古いファイルとの下位互換性を維持したまま形式を変更できるようにする必要があります。 `CArchive::SerializeClass` 関数は、オブジェクトを直接シリアル化する前に、または基底クラスを呼び出す前に明示的に呼び出すことができます。

## <a name="see-also"></a>参照

[番号順テクニカル ノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)
