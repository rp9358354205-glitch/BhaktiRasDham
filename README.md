# BhaktiRasDham
Bhakti Ras Dham bhajan
package com.example.myvideoapp

import android.content.Intent
import android.os.Bundle
import androidx.appcompat.app.AppCompatActivity
import com.google.firebase.auth.FirebaseAuth

class MainActivity : AppCompatActivity() {

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)

        val currentUser =
            FirebaseAuth.getInstance().currentUser

        if (currentUser != null) {
            startActivity(
                Intent(this, HomeActivity::class.java)
            )
        } else {
            startActivity(
                Intent(this, LoginActivity::class.java)
            )
        }

        finish()
    }
}
