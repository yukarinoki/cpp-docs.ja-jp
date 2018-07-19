---
title: 'TN002: 永続オブジェクトのデータ形式 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.data
dev_langs:
- C++
helpviewer_keywords:
- VERSIONABLE_SCHEMA macro [MFC]
- persistent object data
- CArchive class [MFC], support for persistent data
- persistent C++ objects [MFC]
- TN002
ms.assetid: 553fe01d-c587-4c8d-a181-3244a15c2be9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: deca5e0913013e73188e505935d5b2c9b8bf79db
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36952210"
---
# <a name="tn002-persistent-object-data-format"></a>テクニカル ノート 2: 永続オブジェクトのデータ形式
ここでは、ファイルに格納されるときに、永続的な C++ オブジェクトおよびオブジェクトのデータの形式をサポートする MFC ルーチンについて説明します。 これを持つクラスにのみ適用されます、 [DECLARE_SERIAL](../mfc/reference/run-time-object-model-services.md#declare_serial)と[IMPLEMENT_SERIAL](../mfc/reference/run-time-object-model-services.md#implement_serial)マクロです。  
  
## <a name="the-problem"></a>問題を  
 永続的なデータの MFC 実装では、ファイルの 1 つの連続した部品の多くのオブジェクトのデータを格納します。 オブジェクトの`Serialize`メソッドは、コンパクトなバイナリ形式にオブジェクトのデータを変換します。  
  
 実装では、保証を使用して、すべてのデータは、同じ形式で保存、 [CArchive クラス](../mfc/reference/carchive-class.md)です。 使用して、`CArchive`翻訳者オブジェクト。 このオブジェクトは、呼び出されるまでは作成時からが引き続き発生する[CArchive::Close](../mfc/reference/carchive-class.md#close)です。 このメソッドを呼び出せる、プログラマが明示的にまたはデストラクターによって暗黙的にプログラムを含むスコープの終了時、`CArchive`です。  
  
 この注の説明の実装、`CArchive`メンバー [CArchive::ReadObject](../mfc/reference/carchive-class.md#readobject)と[CArchive::WriteObject](../mfc/reference/carchive-class.md#writeobject)です。 Arcobj.cpp との主な実装でこれらの関数のコードを検索するは`CArchive`Arccore.cpp にします。 ユーザー コードを呼び出しません`ReadObject`と`WriteObject`直接です。 代わりに、これらのオブジェクトは、ストリームのマクロで自動的に生成されたクラス固有: タイプ セーフな挿入と抽出演算子によって使用されます。 方法を次のコードに示します`WriteObject`と`ReadObject`は暗黙的に呼び出されます。  
  
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
  
## <a name="saving-objects-to-the-store-carchivewriteobject"></a>ストア (CArchive::WriteObject) にオブジェクトの保存  
 メソッド`CArchive::WriteObject`オブジェクトの再構築に使用されるヘッダーのデータを書き込みます。 このデータは、2 つの部分で構成されています: オブジェクトとオブジェクトの状態の種類。 このメソッドは、(循環ポインターを含む)、そのオブジェクトへのポインターの数に関係なく、1 つのコピーだけが保存されるように、書き出されるオブジェクトの id を保守管理を担当もできます。  
  
 (挿入) を保存し、いくつか「のマニフェスト定数です」に依存しています (展開) のオブジェクトを復元する。 バイナリ形式で格納およびアーカイブ (メモ"w"プレフィックスが 16 ビットの数を示す) に重要な情報を提供する値を次に示します。  
  
|タグ|説明|  
|---------|-----------------|  
|wNullTag|オブジェクトのポインターを NULL (0) に使用されます。|  
|wNewClassTag|このアーカイブ コンテキスト (-1) に新しいに依存しているクラスの説明を示します。|  
|wOldClassTag|このコンテキスト (0x8000) で読み取られているオブジェクトのクラスがあったことを示します。|  
  
 オブジェクトを格納するとき、アーカイブを維持、 [CMapPtrToPtr](../mfc/reference/cmapptrtoptr-class.md) (、 *m_pStoreMap*) が格納されているオブジェクトから 32 ビットの永続的な識別子 (PID) へのマッピング。 PID は、すべての一意のオブジェクトと、アーカイブのコンテキストに保存されているすべての一意のクラス名に割り当てられます。 これら pid は順番に 1 から始まります。 これらの Pid 有意性、アーカイブのスコープ外を持たずには、レコード番号またはその他の識別情報項目と混同しないでください。  
  
 `CArchive`クラス、Pid は 32 ビットは始まりませんが 16 ビットとして 0x7ffe でない限り、します。 大規模な Pid は、32 ビット PID 続けて 0x7FFF として書き込まれます。 これにより、以前のバージョンで作成されたプロジェクトとの互換性が維持されます。  
  
 Null 値のチェックを行う要求が行われると (通常、グローバル挿入演算子を使用) して、アーカイブにオブジェクトを保存する、 [CObject](../mfc/reference/cobject-class.md)ポインター。 ポインターが NULL の場合、 *wNullTag*アーカイブ ストリームに挿入します。  
  
 ポインターが NULL でないと、シリアル化できるかどうか (クラスが、`DECLARE_SERIAL`クラス)、コードのチェック、 *m_pStoreMap*をオブジェクトが既に保存されているかどうかを確認します。 場合に、コードは、アーカイブ ストリームにそのオブジェクトに関連付けられている 32 ビットの PID を挿入します。  
  
 2 つの可能性を考慮する必要がある場合は、オブジェクトが保存されていない: オブジェクトとオブジェクトの正確な型 (つまり、クラス) の両方がこのアーカイブ コンテキストへ新しいまたはオブジェクトが既に固定型のいずれか。 種類が表示されているかどうかを決定するコードのクエリ、 *m_pStoreMap*の[CRuntimeClass](../mfc/reference/cruntimeclass-structure.md)と一致するオブジェクト、`CRuntimeClass`保存されているオブジェクトに関連付けられているオブジェクト。 場合は、一致がある`WriteObject`ビットであるタグを挿入`OR`の*wOldClassTag*し、このインデックス。 場合、`CRuntimeClass`はこのアーカイブ コンテキストへ新しい`WriteObject`そのクラスに新しい PID が割り当てられ、前にする、アーカイブに挿入、 *wNewClassTag*値。  
  
 このクラスの記述子が、挿入を使用して、アーカイブ、`CRuntimeClass::Store`メソッドです。 `CRuntimeClass::Store` クラス (下記参照) のスキーマの数と、ASCII テキスト クラスの名前を挿入します。 ASCII テキスト名の使用によって、アプリケーション間でのアーカイブの一意性が保証されないことに注意してください。 そのため、破損を防ぐため、データ ファイルをタグ付けする必要があります。 次のクラス情報を挿入、アーカイブにオブジェクトを格納、 *m_pStoreMap*しを呼び出して、`Serialize`クラスに固有のデータを挿入するメソッド。 オブジェクトを配置すること、 *m_pStoreMap*呼び出す前に`Serialize`オブジェクトの複数のコピーがストアに保存されないようにします。  
  
 最初の呼び出し元 (通常はオブジェクトのネットワークのルート) を返す、ときに呼び出す必要があります[CArchive::Close](../mfc/reference/carchive-class.md#close)です。 その他を実行する予定の場合[CFile](../mfc/reference/cfile-class.md)操作を呼び出す必要があります、`CArchive`メソッド[フラッシュ](../mfc/reference/carchive-class.md#flush)アーカイブの破損を回避します。  
  
> [!NOTE]
>  この実装は、アーカイブ コンテキストごとインデックス数が 0x3FFFFFFE ハード制限です。 この番号は一意のオブジェクトと 1 つのアーカイブに保存できるクラスの最大数を表しますが、1 つのディスク ファイルがアーカイブ コンテキストの無制限の数を持つことができます。  
  
## <a name="loading-objects-from-the-store-carchivereadobject"></a>ストア (CArchive::ReadObject) からオブジェクトの読み込み  
 オブジェクトを使用して (抽出) を読み込み、`CArchive::ReadObject`メソッドであり、その逆の`WriteObject`します。 同様に`WriteObject`、`ReadObject`ユーザー コードによって直接は呼び出さないユーザー コードはタイプ セーフな抽出演算子を呼び出す必要があります`ReadObject`と、予期された`CRuntimeClass`です。 これにより、抽出操作の型の整合性が保証されます。  
  
 以降、`WriteObject`実装には、1 から始まる増加の Pid が割り当てられている (0 は、NULL オブジェクトとして定義済み)、`ReadObject`実装は、アーカイブ コンテキストの状態を維持するために配列を使用できます。 PID を読み取るときに、ストアからの現在の上限よりも大きい場合は、PID、 *m_pLoadArray*、`ReadObject`新しいオブジェクト (またはクラスの説明) が準拠していることを認識します。  
  
## <a name="schema-numbers"></a>スキーマの番号  
 クラスに割り当てられているスキーマ数と、`IMPLEMENT_SERIAL`クラスのメソッドが発生しましたが、クラスの実装の「バージョン」です。 スキーマ参照クラスの実装、回数が、指定したオブジェクトになりました永続的な (オブジェクトのバージョンと通常呼ばれる)。  
  
 長期にわたって、同じクラスの複数の実装を管理する場合は、オブジェクトの編集した後、スキーマをインクリメント`Serialize`の古いバージョンを使用して、格納されているオブジェクトを読み込むことができるコードを記述するメソッドの実装が有効にします。実装です。  
  
 `CArchive::ReadObject`メソッドがスローされます、 [CArchiveException](../mfc/reference/carchiveexception-class.md)スキーマの数、メモリ内のクラスの説明とは異なる固定ストアのスキーマの数を検出した場合。 この例外から回復する簡単ではありません。  
  
 使用することができます`VERSIONABLE_SCHEMA`と組み合わせる (ビットごと**または**)、スキーマのバージョンをこの例外はスローされませんを保持します。 使用して`VERSIONABLE_SCHEMA`、コード適切な措置をとれるその`Serialize`関数からの戻り値をチェックして[CArchive::GetObjectSchema](../mfc/reference/carchive-class.md#getobjectschema)です。  
  
## <a name="calling-serialize-directly"></a>呼び出し元を直接シリアル化します。  
 多くの場合は、オブジェクトの一般的なアーカイブのスキームのオーバーヘッド`WriteObject`と`ReadObject`必要はありません。 これは、そのデータをシリアル化するは一般的なケースを[CDocument](../mfc/reference/cdocument-class.md)です。 ここで、`Serialize`のメソッド、`CDocument`抽出または挿入演算子ではなく、直接と呼ばれます。 ドキュメントの内容は、一般的なオブジェクト アーカイブ スキームを使用さらに可能性があります。  
  
 呼び出す`Serialize`次の長所と短所を直接には。  
  
-   前にアーカイブする、またはオブジェクトがシリアル化後の追加のバイトが追加されません。 これだけでなく、保存したデータをより小さい、によりが実装することができます`Serialize`ファイル形式のいずれかを処理できるルーチンです。  
  
-   MFC が調整されたため、`WriteObject`と`ReadObject`の実装との関連コレクション リンクされませんをアプリケーションにいくつか他の目的より一般的なオブジェクトのアーカイブ スキームが必要でない限りです。  
  
-   コードは、古いスキーマ番号から復元する必要はありません。 これにより、ドキュメントのシリアル化コードは、エンコード スキーマ番号、ファイル形式のバージョン番号、またはあらゆる識別番号を担当する、データ ファイルの先頭に使用します。  
  
-   任意のオブジェクトへの直接呼び出しでシリアル化される`Serialize`は使用しないでください`CArchive::GetObjectSchema`または必要があります (UINT)-1 の戻り値のハンドルを示すこと、バージョンが不明だった。  
  
 `Serialize`と呼ばれますが、ドキュメント上で直接ことはできません通常、親のドキュメントへの参照をアーカイブするドキュメントのサブオブジェクトのです。 これらのオブジェクトを指定してください、ポインター、コンテナーのドキュメントを明示的にまたは使用する必要があります[CArchive::MapObject](../mfc/reference/carchive-class.md#mapobject)にマップする関数、`CDocument`これらバック ポインターがアーカイブされる前に、PID へのポインター。  
  
 前述のようは、バージョンをエンコードし、クラス情報自分で呼び出すときにする必要があります`Serialize`直接、古いファイルとの下位互換性を維持しながら、形式を後で変更を有効にします。 `CArchive::SerializeClass`直接オブジェクトをシリアル化する前に、または基底クラスを呼び出す前に、関数を明示的に呼び出すことができます。  
  
## <a name="see-also"></a>関連項目  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)

