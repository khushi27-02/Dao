package com.mynotes.notesappmvvmkotlin.Dao

import androidx.lifestyle.LiveData
import androidx.room.*
import com.mynotes.notesappmvvmkotlin.Model.Notes


@Dao
interface NotesDao{
    
    @Query(value "SELECT * FROM Notes")
    fun getNotes(): Livedata<List<Notes>>
    
    @Insert(onconflict = OnConflictStrategy.REPLACE)
    fun insertNotes(notes:Notes)
    
    @Query(value "DELETE FROM Notes WHERE id=:id")
    fun deleteNotes(id:Int)
    
    @Update
    fun updateNotes(notes:Notes)
}
