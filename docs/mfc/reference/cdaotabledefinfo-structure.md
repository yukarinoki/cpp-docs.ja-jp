---
title: CDaoTableDefInfo 構造体 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoTableDefInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoTableDefInfo structure [MFC]
- DAO (Data Access Objects), TableDefs collection
ms.assetid: c01ccebb-5615-434e-883c-4f60eac943dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 80c1422c4d0e45599ca8bc2e9c86a4263b8ac9b6
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36955610"
---
# <a name="cdaotabledefinfo-structure"></a>CDaoTableDefInfo 構造体
`CDaoTableDefInfo`構造体には、データ アクセス オブジェクト (DAO) に対して定義されているテーブル定義のオブジェクトに関する情報が含まれています。  
  
## <a name="syntax"></a>構文  
  
```  
struct CDaoTableDefInfo  
{  
    CString m_strName;               // Primary  
    BOOL m_bUpdatable;               // Primary  
    long m_lAttributes;              // Primary  
    COleDateTime m_dateCreated;      // Secondary  
    COleDateTime m_dateLastUpdated;  // Secondary  
    CString m_strSrcTableName;       // Secondary  
    CString m_strConnect;            // Secondary  
    CString m_strValidationRule;     // All  
    CString m_strValidationText;     // All  
    long m_lRecordCount;             // All  
};  
```  
  
#### <a name="parameters"></a>パラメーター  
 *m_strName*  
 テーブル定義オブジェクトの一意名です。 このプロパティの値を直接取得する呼び出し定義オブジェクトの[GetName](../../mfc/reference/cdaotabledef-class.md#getname)メンバー関数。 詳細については、DAO ヘルプの「名前プロパティ」を参照してください。  
  
 *m_bUpdatable*  
 変更をテーブルにできるかどうかを示します。 テーブルが更新可能かどうかを決定するすばやく開くには、`CDaoTableDef`テーブルのオブジェクトし、オブジェクトの[CanUpdate](../../mfc/reference/cdaotabledef-class.md#canupdate)メンバー関数。 `CanUpdate` 常に 0 以外を返します (**TRUE**) の新しく作成されたテーブル定義オブジェクトおよび 0 (**FALSE**) のアタッチされたテーブル定義オブジェクト。 新しいテーブル定義オブジェクトは、現在のユーザーが書き込みアクセス許可を持っているデータベースにのみ追加できます。 テーブルには、更新できないフィールドのみが含まれている場合`CanUpdate`0 を返します。 1 つまたは複数のフィールドが更新可能な`CanUpdate`0 以外を返します。 更新可能なフィールドのみを編集することができます。 詳細については、DAO ヘルプの「更新可能なプロパティ」を参照してください。  
  
 *m_lAttributes*  
 テーブル定義オブジェクトによって表されるテーブルの特性を指定します。 テーブル定義の現在の属性を取得するその[GetAttributes](../../mfc/reference/cdaotabledef-class.md#getattributes)メンバー関数。 返される値の長さの定数の組み合わせが可能です (ビットごとの OR を使用して (**&#124;**) 演算子)。  
  
- **dbAttachExclusive** Microsoft Jet データベース エンジンを使用するデータベース、テーブルは排他的に開かれてアタッチ テーブルことを示します。  
  
- **dbAttachSavePWD** Microsoft Jet データベース エンジンを使用するデータベース、接続情報を持つユーザー ID とパスワード、接続されているテーブルを保存することを示します。  
  
- **dbSystemObject**テーブルが、Microsoft Jet データベース エンジンによって提供されるシステム テーブルであることを示します。 システム テーブルは読み取り専用です。  
  
- **dbHiddenObject**テーブルが一時的に使用) (Microsoft Jet データベース エンジンによって提供される隠しテーブルであることを示します。 システム テーブルは読み取り専用です。  
  
- **dbAttachedTable**テーブルが Paradox データベースなどの非 ODBC データベースからのアタッチのテーブルであることを示します。  
  
- **dbAttachedODBC**テーブルが Microsoft SQL Server などの ODBC データベースからのアタッチのテーブルであることを示します。  
  
 *m_dateCreated*  
 日付と、テーブルが作成された時刻。 テーブルが作成された日付を直接取得する呼び出し、 [GetDateCreated](../../mfc/reference/cdaotabledef-class.md#getdatecreated)のメンバー関数、`CDaoTableDef`テーブルに関連付けられているオブジェクト。 詳細については、下のコメントを参照してください。 関連情報については、DAO ヘルプのトピックの「作成日時、LastUpdated プロパティ」を参照してください。  
  
 *m_dateLastUpdated*  
 日付と、テーブルのデザインに加えられた最近の変更時刻。 テーブルの最終更新日を直接取得する呼び出し、 [GetDateLastUpdated](../../mfc/reference/cdaotabledef-class.md#getdatelastupdated)のメンバー関数、`CDaoTableDef`テーブルに関連付けられているオブジェクト。 詳細については、下のコメントを参照してください。 関連情報については、DAO ヘルプのトピックの「作成日時、LastUpdated プロパティ」を参照してください。  
  
 *m_strSrcTableName*  
 存在する場合は、接続されているテーブルの名前を指定します。 ソース テーブル名を直接取得する呼び出し、 [GetSourceTableName](../../mfc/reference/cdaotabledef-class.md#getsourcetablename)のメンバー関数、`CDaoTableDef`テーブルに関連付けられているオブジェクト。  
  
 *m_strConnect*  
 開いているデータベースのソースに関する情報を提供します。 このプロパティを確認するには呼び出すことによって、 [GetConnect](../../mfc/reference/cdaotabledef-class.md#getconnect)のメンバー関数、`CDaoTableDef`オブジェクト。 詳細については、接続文字列を参照してください`GetConnect`です。  
  
 *m_strValidationRule*  
 そのまま変更テーブルに追加のテーブル定義のフィールドのデータを検証する値。 検証方法は、Microsoft Jet データベース エンジンを使用するデータベースにのみサポートされます。 検証規則を直接取得する呼び出し、 [GetValidationRule](../../mfc/reference/cdaotabledef-class.md#getvalidationrule)のメンバー関数、`CDaoTableDef`テーブルに関連付けられているオブジェクト。 関連情報については、"Validationrule"DAO ヘルプのトピックを参照してください。  
  
 *m_strValidationText*  
 プロパティで指定された検証規則が満たされていない場合、アプリケーションを表示するメッセージのテキストを指定する値。 関連情報については、「プロパティ」DAO ヘルプのトピックを参照してください。  
  
 *m_lRecordCount*  
 テーブル定義オブジェクトにアクセスするレコードの数。 このプロパティの設定は、読み取り専用です。 レコード カウントを直接取得する呼び出し、 [GetRecordCount](../../mfc/reference/cdaotabledef-class.md#getrecordcount)のメンバー関数、`CDaoTableDef`オブジェクト。 ドキュメントを`GetRecordCount`レコード数の詳細について説明します。 この数を取得できる時間のかかる操作、テーブルに多数のレコードが含まれている場合に注意してください。  
  
## <a name="remarks"></a>Remarks  
 クラスのオブジェクトは、テーブル定義[どちら](../../mfc/reference/cdaotabledef-class.md)です。 プライマリ、セカンダリ、および上記のすべての参照は、情報がによって返される方法を示します、[プライマリ](../../mfc/reference/cdaodatabase-class.md#gettabledefinfo)クラスのメンバー関数`CDaoDatabase`です。  
  
 によって取得される情報、 [cdaodatabase::gettabledefinfo](../../mfc/reference/cdaodatabase-class.md#gettabledefinfo)メンバー関数は、`CDaoTableDefInfo`構造体。 呼び出す、`GetTableDefInfo`のメンバー関数、 `CDaoDatabase` TableDefs コレクションでのテーブル定義オブジェクトが格納されているオブジェクト。 `CDaoTableDefInfo` 定義、`Dump`デバッグでメンバー関数を作成します。 使用することができます`Dump`の内容をダンプする`CDaoTableDefInfo`オブジェクト。  
  
 日付と時刻の設定は、ベース テーブルが作成または最後に更新されたコンピューターから派生します。 マルチ ユーザー環境では、ユーザーはこれらのファイル サーバーから直接、DateCreated で不一致を避けるための設定と LastUpdated のプロパティの設定を取得する必要があります。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxdao.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [どちらのクラス](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoDatabase クラス](../../mfc/reference/cdaodatabase-class.md)
