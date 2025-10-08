# Motion Type Identifier

# Function 1: Convert velocity to m/s
def convert_velocity(value, unit):
    """
    Convert velocity to meters per second (m/s)
    Supported units: m/s, ft/s, km/s, mi/s
    """
    if unit == "m/s":
        return value
    elif unit == "ft/s":
        return value * 0.3048
    elif unit == "km/s":
        return value * 1000
    elif unit == "mi/s":
        return value * 1609.34
    else:
        print("Unsupported velocity unit.")
        return None


# Function 2: Convert acceleration to m/s²
def convert_acceleration(value, unit):
    """
    Convert acceleration to meters per second squared (m/s²)
    Supported units: m/s², ft/s², km/s², mi/s²
    """
    if unit == "m/s²":
        return value
    elif unit == "ft/s²":
        return value * 0.3048
    elif unit == "km/s²":
        return value * 1000
    elif unit == "mi/s²":
        return value * 1609.34
    else:
        print("Unsupported acceleration unit.")
        return None


# Function 3: Determine motion type
def motion_type(v, a):
    """
    Determine the type of motion based on velocity and acceleration
    Rules:
    - v > 0 and a = 0 → "Uniform Motion"
    - v > 0 and a > 0 → "Accelerated Motion"
    - v > 0 and a < 0 → "Decelerated Motion"
    - v = 0 → "At Rest"
    """
    if v == 0:
        return "At Rest"
    elif v > 0 and a == 0:
        return "Uniform Motion"
    elif v > 0 and a > 0:
        return "Accelerated Motion"
    elif v > 0 and a < 0:
        return "Decelerated Motion"
    else:
        return "Unknown Motion"


# --- Main Program ---

# Step 1: Input velocity
v_value = float(input("Enter velocity value: "))
v_unit = input("Enter velocity unit (m/s, ft/s, km/s, mi/s): ")

# Step 2: Input acceleration
a_value = float(input("Enter acceleration value: "))
a_unit = input("Enter acceleration unit (m/s², ft/s², km/s², mi/s²): ")

# Step 3: Convert to SI units
v_si = convert_velocity(v_value, v_unit)      
# Call the conversion function
a_si = convert_acceleration(a_value, a_unit)  
# Call the conversion function
# Step 4: Determine motion type
motion = motion_type(v_si, a_si)             

 # Call the motion type function
# Step 5: Display results
print("\n--- Results ---")
print(f"Velocity = {v_si:.3f} m/s")
print(f"Acceleration = {a_si:.3f} m/s²")
print(f"Motion Type = {motion}")