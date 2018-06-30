---
title: CDaoIndexInfo 構造体 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/25/2018
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoIndexInfo
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), Indexes collection
- CDaoIndexInfo structure [MFC]
ms.assetid: 251d8285-78ce-4716-a0b3-ccc3395fc437
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7d07193e43198797b31519b042b9f813676e08c2
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2018
ms.locfileid: "37121458"
---
# <a name="cdaoindexinfo-structure"></a>CDaoIndexInfo 構造体

`CDaoIndexInfo`構造体には、データ アクセス オブジェクト (DAO) に対して定義されているインデックス オブジェクトに関する情報が含まれています。

## <a name="syntax"></a>構文

```cpp
struct CDaoIndexInfo {
    CDaoIndexInfo();                    // Constructor
    CString m_strName;                  // Primary
    CDaoIndexFieldInfo* m_pFieldInfos;  // Primary
    short m_nFields;                    // Primary
    BOOL m_bPrimary;                    // Secondary
    BOOL m_bUnique;                     // Secondary
    BOOL m_bClustered;                  // Secondary
    BOOL m_bIgnoreNulls;                // Secondary
    BOOL m_bRequired;                   // Secondary
    BOOL m_bForeign;                    // Secondary
    long m_lDistinctCount;              // All

    // Below the // Implementation comment:
    // Destructor, not otherwise documented
};
```

### <a name="parameters"></a>パラメーター

*m_strName*  
フィールド オブジェクトの一意名です。 詳細については、DAO ヘルプの「名前プロパティ」を参照してください。

*m_pFieldInfos*  
配列へのポインター [CDaoIndexFieldInfo](../../mfc/reference/cdaoindexfieldinfo-structure.md) tabledef またはレコード セット フィールドは、インデックスのキー フィールドを示すオブジェクト。 各オブジェクトは、インデックス内の 1 つのフィールドを識別します。 既定のインデックス順序は昇順です。 Index オブジェクトは、各レコードのインデックス キーを表す 1 つまたは複数のフィールドを持つことができます。 これらは、降順、または組み合わせ、昇順ことができます。

*m_nFields*  
格納されているフィールド数`m_pFieldInfos`です。

*m_bPrimary*  
プライマリ プロパティが場合**TRUE**、index オブジェクトは、プライマリ インデックスを表します。 プライマリ インデックスは、定義済みの順序でテーブル内のすべてのレコードを一意に識別する 1 つ以上のフィールドで構成されます。 Index オブジェクトの一意のプロパティに設定もインデックスのフィールドは一意である必要があります、ため**TRUE** DAO でします。 場合は、プライマリ インデックスは、1 つ以上のフィールドで構成される、各フィールドは、重複する値を含めることができますが、すべてのインデックス付きフィールドの値の組み合わせは一意である必要があります。 プライマリ インデックスは、テーブルのキーで構成され、通常、主キーと同じフィールドが含まれます。

テーブルの主キーを設定すると、主キーがテーブルのプライマリ インデックスとして自動的に定義します。 詳細については、"プライマリ Property"および「一意のプロパティ」DAO ヘルプ トピックを参照してください。

> [!NOTE]
> あります、多くても、テーブルの 1 つのプライマリ インデックス。

*m_bUnique*  
Index オブジェクトがテーブルの一意のインデックスを表すかどうかを示します。 このプロパティは、する場合**TRUE**、インデックス オブジェクトが一意であるインデックスを表します。 一意のインデックスは、一意で、定義済みの順序で、テーブルのすべてのレコードを論理的に整列する 1 つ以上のフィールドで構成されます。 場合は、インデックスは、1 つのフィールドで構成される、そのフィールドに値がテーブル全体で一意でなければなりません。 インデックスは、複数のフィールドで構成され場合、は、各フィールドは、重複する値を含めることができますが、すべてのインデックス付きフィールドの値の組み合わせは一意である必要があります。

インデックス オブジェクトの Unique とプライマリの両方のプロパティが設定されている場合**TRUE**インデックスが一意でプライマリ: 定義済みの論理的な順序でテーブルのすべてのレコードを一意に識別します。 プライマリのプロパティ設定されている場合**FALSE**インデックスがセカンダリ インデックス。 (キー、非キー) のセカンダリ インデックスは、テーブル内のレコードの識別子としては機能しません、定義済みの順序でレコードを論理的に配置します。

詳細については、"プライマリ Property"および「一意のプロパティ」DAO ヘルプ トピックを参照してください。

*m_bClustered*  
Index オブジェクトがテーブルのクラスター化インデックスを表すかどうかを示します。 場合は、このプロパティは**TRUE**、インデックス オブジェクトは、クラスター化インデックスを表すです。 それ以外の場合はありません。 クラスター化インデックスから成る 1 つまたは複数の非キー フィールドで、定義済みの順序でテーブル内のすべてのレコードをまとめると、配置します。 クラスター化インデックス、テーブル内のデータはそのまま、クラスター化インデックスで指定された順序に格納されます。 クラスター化インデックスは、テーブル内のレコードに効率的にアクセスを提供します。 詳細については、「クラスター化されたプロパティ」DAO ヘルプのトピックを参照してください。

> [!NOTE]
> Jet データベース エンジンがクラスター化インデックスをサポートしていないために、Microsoft Jet データベース エンジンを使用するデータベースをクラスター化されたプロパティは無視されます。

*m_bIgnoreNulls*  
インデックス フィールドに Null 値を持つレコードのインデックス エントリがあるかどうかを示します。 場合は、このプロパティは**TRUE**Null 値を持つフィールドには、インデックス エントリはありません。 フィールドを高速化を使用してレコードを検索するには、フィールドのインデックスを定義できます。 インデックス付きフィールドの Null エントリを許可するし、Null にできるエントリの多くは、するインデックス オブジェクトの IgnoreNulls プロパティを設定することができます**TRUE**インデックスによって使用される記憶域スペースの量を削減します。 IgnoreNulls プロパティの設定と必要なプロパティの設定は、同時に Null インデックス値を持つレコードが次の表に示すように、インデックス エントリを持つかどうかを決定します。

|IgnoreNulls|必須|インデックスのフィールド内の null 値します。|
|-----------------|--------------|-------------------------|
|True|False|Null 値が許可されます。インデックス エントリを追加します。|
|False|False|Null 値が許可されます。インデックス エントリが追加されました。|
|True または False|True|Null 値が許可されていません。インデックス エントリを追加します。|

詳細については、DAO ヘルプの「IgnoreNulls プロパティ」を参照してください。

*m_bRequired*  
DAO インデックス オブジェクトに Null 以外の値が必要かどうかを示します。 このプロパティは、する場合**TRUE**、インデックス オブジェクトが Null 値を許可しません。 詳細については、「必要なプロパティ」DAO ヘルプ トピックを参照してください。

> [!TIP]
> DAO インデックス オブジェクト、または (tabledef、レコード セット、またはクエリ定義オブジェクトに含まれる) のフィールド オブジェクトのこのプロパティを設定するときに、フィールド オブジェクトに設定します。 Field オブジェクトのプロパティの設定の有効性が、そのインデックス オブジェクトの前にチェックされます。

*m_bForeign*  
Index オブジェクトがテーブルの外部キーを表すかどうかを示します。 このプロパティは、する場合**TRUE**インデックスは、テーブルの外部キーを表します。 外部キーは、主テーブル内の行を一意に識別する外部キー テーブルの 1 つまたは複数のフィールドで構成されます。 Microsoft Jet データベース エンジンは、外部テーブルのインデックス オブジェクトを作成し、参照整合性を適用するリレーションシップを作成するときに、外部のプロパティを設定します。 詳細については、DAO ヘルプの「外部プロパティ」を参照してください。

*m_lDistinctCount*  
関連付けられているテーブルに含まれているインデックス オブジェクトの一意の値の数を示します。 一意の値、またはインデックス内のキーの数を決定する、DistinctCount プロパティを確認します。 任意のキーは 1 回だけカウントされる場合でも、インデックスが重複する値を許可している場合、その値の複数の発生にすることがあります。 この情報は、インデックスの情報を評価することによってデータ アクセスを最適化しようとするアプリケーションで役に立ちます。 一意の値の数は、インデックス オブジェクトの基数とも呼ばれます。 DistinctCount プロパティ常に反映されませんキーの実際の数、特定の時点。 たとえば、トランザクションのロールバックによって発生する変更反映されません直ちに DistinctCount プロパティにします。 詳細については、DAO ヘルプの「DistinctCount プロパティ」を参照してください。

## <a name="remarks"></a>Remarks

プライマリ、セカンダリ、および上記のすべての参照は、情報がによって返される方法を示します、`GetIndexInfo`クラスでメンバー関数[どちら](../../mfc/reference/cdaotabledef-class.md#getindexinfo)と[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getindexinfo)です。

Index オブジェクトは、MFC クラスでは表されません。 DAO オブジェクト クラスの基になる MFC オブジェクトの代わりに、[どちら](../../mfc/reference/cdaotabledef-class.md)または[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)インデックス コレクションと呼ばれるインデックス オブジェクトのコレクションを格納します。 これらのクラスは、インデックス情報の各アイテムにアクセスするメンバー関数を指定するか、すべて同時にアクセスすることができます、`CDaoIndexInfo`オブジェクトを呼び出して、`GetIndexInfo`親オブジェクトのメンバー関数。

`CDaoIndexInfo` コンス トラクターとデストラクターが正しく割り当ておよびでインデックスのフィールド情報を解放するために`m_pFieldInfos`です。

によって取得される情報、`GetIndexInfo`テーブル定義オブジェクトのメンバー関数は、`CDaoIndexInfo`構造体。 呼び出す、`GetIndexInfo`インデックス オブジェクトが格納されているコレクションを持つインデックスを含むテーブル定義オブジェクトのメンバー関数。 `CDaoIndexInfo` 定義、`Dump`デバッグでメンバー関数を作成します。 使用することができます`Dump`の内容をダンプする`CDaoIndexInfo`オブジェクト。

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdao.h

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)  
[CDaoTableDef::GetIndexInfo](../../mfc/reference/cdaotabledef-class.md#getindexinfo)  
