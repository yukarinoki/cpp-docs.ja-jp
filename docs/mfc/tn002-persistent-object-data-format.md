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
ms.openlocfilehash: f65a7b7afcf6bd832c9c23560bb29374038fae1b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370452"
---
# <a name="tn002-persistent-object-data-format"></a>テクニカル ノート 2: 永続オブジェクトのデータ形式

このノートでは、永続的な C++ オブジェクトをサポートする MFC ルーチンと、ファイルに格納されているオブジェクト データの形式について説明します。 これは[、DECLARE_SERIAL](../mfc/reference/run-time-object-model-services.md#declare_serial)と[IMPLEMENT_SERIAL](../mfc/reference/run-time-object-model-services.md#implement_serial)マクロを持つクラスにのみ適用されます。

## <a name="the-problem"></a>問題

永続データの MFC 実装では、ファイルの連続した単一部分に多数のオブジェクトのデータを格納します。 オブジェクトの`Serialize`メソッドは、オブジェクトのデータをコンパクトなバイナリ形式に変換します。

この実装では[、CArchive クラス](../mfc/reference/carchive-class.md)を使用して、すべてのデータが同じ形式で保存されます。 オブジェクトを`CArchive`トランスレータとして使用します。 このオブジェクトは、作成された時点から[CArchive::Close](../mfc/reference/carchive-class.md#close)を呼び出すまで保持されます。 このメソッドは、プログラマが明示的に呼び出すか、またはプログラムが`CArchive`を含むスコープを終了するときにデストラクターによって暗黙的に呼び出すことができます。

このメモでは、`CArchive`[メンバー CArchive::ReadObject](../mfc/reference/carchive-class.md#readobject)と[CArchive::WriteObject の実装について説明します](../mfc/reference/carchive-class.md#writeobject)。 これらの関数のコードは Arcobj.cpp にあり、Arccore.cpp`CArchive`の主な実装も確認できます。 ユーザー コードは直接`ReadObject`呼`WriteObject`び出しません。 代わりに、これらのオブジェクトは、DECLARE_SERIALおよびIMPLEMENT_SERIALマクロによって自動的に生成されるクラス固有のタイプ セーフな挿入および抽出演算子によって使用されます。 次のコードは、`WriteObject`どのように`ReadObject`暗黙的に呼び出されるのかを示しています。

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

## <a name="saving-objects-to-the-store-carchivewriteobject"></a>オブジェクトを保存する (CArchive::WriteObject)

このメソッド`CArchive::WriteObject`は、オブジェクトの再構築に使用されるヘッダー データを書き込みます。 このデータは、オブジェクトの型とオブジェクトの状態という 2 つの部分で構成されます。 このメソッドは、書き出されるオブジェクトの ID を保持する役割も果たします。

オブジェクトの保存 (挿入) と復元 (抽出) は、いくつかの 「マニフェスト定数」に依存します。 これらはバイナリで格納され、アーカイブに重要な情報を提供する値です ("w" 接頭辞は 16 ビットの量を示します)。

|タグ|説明|
|---------|-----------------|
|タグ|NULL オブジェクト ポインタ (0) に使用されます。|
|をクリックします。|このアーカイブ コンテキストに新しく追加されたクラスの説明 (-1) を示します。|
|クラスタグ|読み取られるオブジェクトのクラスがこのコンテキストで見られたことを示します (0x8000)。|

オブジェクトを格納する場合、アーカイブは[CMapPtrToPtr](../mfc/reference/cmapptrtoptr-class.md) *(m_pStoreMap)* を保持します。 PID は、アーカイブのコンテキストに保存されるすべての一意のオブジェクトとすべての固有のクラス名に割り当てられます。 これらの PID は、1 から順に渡されます。 これらの PID はアーカイブの範囲外では意味を持たないので、特にレコード番号やその他の ID 項目と混同しないでください。

`CArchive`このクラスでは、PID は 32 ビットですが、0x7FFE より大きい場合を除き、16 ビットとして書き出されます。 大きな PID は 0x7FFF の後に 32 ビット PID として書き込まれます。 これにより、以前のバージョンで作成されたプロジェクトとの互換性が維持されます。

オブジェクトをアーカイブに保存する要求が行われると (通常はグローバル挿入演算子を使用して)、NULL [CObject](../mfc/reference/cobject-class.md)ポインタがチェックされます。 ポインタが NULL の場合 *、wNullTag*がアーカイブ ストリームに挿入されます。

ポインターが NULL ではなく、シリアル化できる場合 (クラスクラス`DECLARE_SERIAL`)、オブジェクトが既に保存されているかどうかを確認するために*m_pStoreMap*をチェックします。 その場合、コードは、そのオブジェクトに関連付けられている 32 ビット PID をアーカイブ ストリームに挿入します。

オブジェクトが以前に保存されていない場合、オブジェクトとオブジェクトの正確な型 (つまり、クラス) の両方がこのアーカイブ コンテキストに新しいか、オブジェクトが既に見られる正確な型であるかの 2 つの方法があります。 型が見られたかどうかを確認するために、コードは、保存されるオブジェクトに関連付けられているオブジェクトと一致する`CRuntimeClass`[CRuntimeClass](../mfc/reference/cruntimeclass-structure.md)オブジェクトの*m_pStoreMap*を照会します。 一致する場合は`WriteObject`*、wOldClassTag*とこのインデックスのビット`OR`単位のタグを挿入します。 このアーカイブ`CRuntimeClass`コンテキストに新しいが存在`WriteObject`する場合は、そのクラスに新しい PID を割り当て、その PID をアーカイブに*挿入します。*

このクラスの記述子は、メソッドを使用してアーカイブに挿入されます`CRuntimeClass::Store`。 `CRuntimeClass::Store`クラスのスキーマ番号 (下記参照) とクラスの ASCII テキスト名を挿入します。 ASCII テキスト名を使用しても、アプリケーション間でアーカイブの一意性が保証されるわけではありません。 したがって、データ ファイルにタグを付け、破損を防ぐ必要があります。 クラス情報の挿入後、アーカイブはオブジェクトを*m_pStoreMap*に入れ、メソッドを`Serialize`呼び出してクラス固有のデータを挿入します。 呼び出す`Serialize`前にオブジェクトを*m_pStoreMap*に配置すると、オブジェクトの複数のコピーがストアに保存されなくなります。

最初の呼び出し元 (通常はオブジェクトのネットワークのルート) に戻る場合は[、CArchive::Close](../mfc/reference/carchive-class.md#close)を呼び出す必要があります。 他の[CFile](../mfc/reference/cfile-class.md)操作を実行する場合は、アーカイブ`CArchive`の破損を防ぐためにメソッド[Flush](../mfc/reference/carchive-class.md#flush)を呼び出す必要があります。

> [!NOTE]
> この実装では、アーカイブコンテキストごとに 0x3FFFFFFE インデックスのハード制限が適用されます。 この数は、1 つのアーカイブに保存できる一意のオブジェクトとクラスの最大数を表しますが、1 つのディスク ファイルにアーカイブ コンテキストの数を制限することはできません。

## <a name="loading-objects-from-the-store-carchivereadobject"></a>ストアからのオブジェクトの読み込み (CArchive::ReadObject)

オブジェクトの読み込み (`CArchive::ReadObject`抽出) は、`WriteObject`の逆のメソッドを使用します。 と同様`WriteObject`に`ReadObject`、ユーザー コードによって直接呼び出されるわけではありません。ユーザー コードは、予期される`ReadObject``CRuntimeClass`を呼び出すタイプ セーフな抽出演算子を呼び出す必要があります。 これにより、抽出操作の型の整合性が保証されます。

実装では`WriteObject`、1 (0 は NULL オブジェクトとして事前定義) から、PID`ReadObject`の増加を割り当てるため、実装では、配列を使用してアーカイブ コンテキストの状態を維持できます。 PID がストアから読み取られると、pid が*m_pLoadArray現在の上限*より大きい場合`ReadObject`は、新しいオブジェクト (またはクラスの説明) が次のとおりであることを認識します。

## <a name="schema-numbers"></a>スキーマ番号

クラスの`IMPLEMENT_SERIAL`メソッドが検出されたときにクラスに割り当てられるスキーマ番号は、クラス実装の「バージョン」です。 スキーマは、特定のオブジェクトが永続 (通常はオブジェクト バージョンと呼ばれます) が行われた回数ではなく、クラスの実装を参照します。

同じクラスの複数の異なる実装を時間の経過と同時に維持する場合、オブジェクトの`Serialize`メソッド実装を変更するときにスキーマをインクリメントすると、古いバージョンの実装を使用して格納されたオブジェクトを読み込むことができるコードを記述できます。

この`CArchive::ReadObject`メソッドは、永続ストア内で、メモリ内のクラス記述のスキーマ番号とは異なるスキーマ番号を検出すると[、CArchiveException](../mfc/reference/carchiveexception-class.md)をスローします。 この例外から回復するのは容易ではありません。

スキーマバージョン`VERSIONABLE_SCHEMA`(ビットごとの**OR)** と組み合わせて使用すると、この例外がスローされないようにすることができます。 を使用`VERSIONABLE_SCHEMA`すると、コードは`Serialize`[CArchive::GetObjectSchema](../mfc/reference/carchive-class.md#getobjectschema)からの戻り値をチェックすることで、関数内で適切なアクションを実行できます。

## <a name="calling-serialize-directly"></a>シリアル化を直接呼び出す

多くの場合、一般オブジェクトアーカイブ方式の`WriteObject`オーバーヘッドは不要`ReadObject`です。 これは、データを[CDocument](../mfc/reference/cdocument-class.md)にシリアル化する一般的なケースです。 この場合、の`Serialize`メソッド`CDocument`は、抽出演算子または挿入演算子ではなく、直接呼び出されます。 文書の内容は、より一般的なオブジェクトアーカイブスキームを使用する場合があります。

直接`Serialize`呼び出す場合、次の長所と短所があります。

- オブジェクトがシリアル化される前または後に、アーカイブに追加されたバイト数は追加されません。 これにより、保存されたデータが小さくなるだけでなく、任意のファイル`Serialize`形式を処理できるルーチンを実装できます。

- MFC は、他の`WriteObject`目的`ReadObject`のためにより一般的なオブジェクト アーカイブスキームが必要な場合を除き、 および 実装と関連するコレクションがアプリケーションにリンクしないように調整されています。

- コードは、古いスキーマ番号から回復する必要はありません。 これにより、スキーマ番号、ファイル形式のバージョン番号、またはデータ ファイルの先頭で使用する識別番号をエンコードするドキュメントシリアル化コードが行われます。

- 直接呼び出し`Serialize`を使用してシリアル化されるオブジェクトは、`CArchive::GetObjectSchema`バージョンが不明であることを示す (UINT)-1 の戻り値を使用しないか、または処理する必要があります。

ドキュメント`Serialize`に直接呼び出されるため、通常、ドキュメントのサブオブジェクトが親ドキュメントへの参照をアーカイブすることはできません。 これらのオブジェクトは、コンテナー ドキュメントへのポインターを明示的に与える必要[CArchive::MapObject](../mfc/reference/carchive-class.md#mapobject)`CDocument`があります。

前述のように、直接呼び出`Serialize`すときにバージョンとクラスの情報を自分でエンコードし、古いファイルとの下位互換性を維持しながら、後でフォーマットを変更できるようにする必要があります。 この`CArchive::SerializeClass`関数は、オブジェクトを直接シリアル化する前、または基本クラスを呼び出す前に明示的に呼び出すことができます。

## <a name="see-also"></a>関連項目

[番号順テクニカル ノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)
