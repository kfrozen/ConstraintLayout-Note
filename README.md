## ConstraintLayout Note ##

- Firstly, give your ConstraintLayout an id, see below

	    <android.support.constraint.ConstraintLayout
        	android:id="@+id/parent_constraint"
        	android:layout_width="match_parent"
        	android:layout_height="wrap_content">

- Convert from LinearLayout/RelativeLayout

	- layout-gravity="center_vertical" / layout-centerInVertical="true"

			app:layout_constraintTop_toTopOf="@id/parent_constraint"
          	app:layout_constraintBottom_toBottomOf="@id/parent_constraint"
          	
    - layout-gravity="center_horizontal" / layout-centerInHorizontal="true"

    		app:layout_constraintStart_toStartOf="@id/parent_constraint"
          	app:layout_constraintEnd_toEndOf="@id/parent_constraint"
          	
    - layout-gravity="center" / layout-centerInParent="true"

    		app:layout_constraintStart_toStartOf="@id/parent_constraint"
          	app:layout_constraintEnd_toEndOf="@id/parent_constraint"
          	app:layout_constraintTop_toTopOf="@id/parent_constraint"
          	app:layout_constraintBottom_toBottomOf="@id/parent_constraint"
          	
    - weight

    		app:layout_constraintHorizontal_weight="x"
    		OR
            app:layout_constraintVertical_weight="x"
            
	- layout-alignParentStart="true"

			app:layout_constraintStart_toStartOf="@id/parent_constraint"
			
	- layout-alignParentEnd="true"

			app:layout_constraintEnd_toEndOf="@id/parent_constraint"
			
	- layout-alignParentTop="true"

			app:layout_constraintTop_toTopOf="@id/parent_constraint"
			
	- layout-alignParentBottom="true"

			app:layout_constraintBottom_toBottomOf="@id/parent_constraint"
			
	- layout-toStartOf="@id/xxx"

			app:layout_constraintEnd_toStartOf="@id/xxx"
			
	- layout-toEndOf="@id/xxx"

			app:layout_constraintStart_toEndOf="@id/xxx"
			
	- layout-above="@id/xxx"

			app:layout_constraintBottom_toTopOf="@id/xxx"
			
	- layout-below="@id/xxx"

			app:layout_constraintTop_toBottomOf="@id/xxx"
			
- Replacement of "match_parent"

	Since ConstraintLayout does not support attr "match_parent" for width or height, we need to do delow as an alternative way:
	
		before:
		android:layout_width="match_parent"
        android:layout_height="wrap_content"
        
        after:
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        app:layout_constraintStart_toStartOf="@id/parent_constraint"
        app:layout_constraintEnd_toEndOf="@id/parent_constraint"
        
- Fixed Ratio

	The code below indicates an ImageView whose width is "match_parent" while height is defined by the width to height ratio 16:9
	
		<ImageView
        	android:layout_width="0dp"
        	android:layout_height="0dp"
            app:layout_constraintLeft_toLeftOf="@+id/parent_constraint"
        	app:layout_constraintRight_toRightOf="@+id/parent_constraint"
        	app:layout_constraintDimensionRatio="16:9"/>
        	
- Other new attributes

	- Guideline
	- percent
	- bias
	- chainStyle
          	
    
